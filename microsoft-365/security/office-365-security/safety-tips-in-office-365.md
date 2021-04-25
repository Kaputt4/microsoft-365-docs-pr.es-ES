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
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo EOP y Office 365 le protegen con correo no deseado, phishing y prevención de malware agregando una sugerencia de seguridad a la parte superior de los correos electrónicos.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 659a83c73b4fef9097aa317332c9951d53b09a33
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994990"
---
# <a name="safety-tips-in-email-messages"></a>Sugerencias de seguridad en mensajes de correo electrónico

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) y Microsoft 365 le protegen con correo no deseado, phishing y prevención de malware. Hoy en día, algunos de estos ataques están tan bien diseñados que parecen legítimos. Enviar mensajes a la carpeta correo no deseado no siempre es suficiente. Ahora, cuando comprueba el correo electrónico en Outlook o Outlook en la web o en cualquier cliente de correo electrónico, EOP comprueba automáticamente al remitente y agrega una sugerencia de seguridad a la parte superior del correo electrónico.

Las sugerencias de seguridad en Outlook no dependen de la versión de Outlook que esté usando porque la sugerencia de seguridad está abierta e insertada directamente en el cuerpo del mensaje. Esto significa que la sugerencia de seguridad aparecerá en cualquier cliente de correo electrónico que estés usando. Se realiza en el nivel de filtro de correo electrónico y no se representa en el nivel de cliente de correo, por lo que no solo se muestra en cualquier versión de Outlook, sino que también se muestra en cualquier cliente de correo electrónico.

La sugerencia de seguridad , un mensaje codificado por colores, le advertirá sobre mensajes potencialmente dañinos. La mayoría de los mensajes de la bandeja de entrada no tendrán una sugerencia de seguridad. Solo las verás cuando EOP y Microsoft 365 tengan información que necesites para evitar ataques de correo no deseado, suplantación de identidad (phishing) y malware. Si las sugerencias de seguridad se muestran en la bandeja de entrada, puede usar los siguientes ejemplos para obtener más información sobre cada tipo de sugerencia de seguridad.

- Correo sospechoso (sugerencia de seguridad roja).

    ![Captura de pantalla que muestra una sugerencia de seguridad roja.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Una sugerencia de seguridad roja en un correo electrónico significa que el mensaje que recibió contiene algo sospechoso, como una estafa de phishing. Se recomienda eliminar este tipo de mensaje de correo electrónico de la bandeja de entrada sin abrirlo.

- Correo seguro (sugerencia de seguridad verde).

    ![Captura de pantalla que muestra una sugerencia de seguridad verde.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Además de los mensajes no seguros, también le contaremos los mensajes válidos de remitentes en los que confiamos con una sugerencia de seguridad verde. Una sugerencia de seguridad verde en un correo electrónico significa que hemos comprobado el remitente del mensaje y comprobado que es seguro. Microsoft mantiene esta lista de remitentes de confianza que incluye organizaciones financieras y otras que con frecuencia se suplantan o suplantan.

## <a name="working-with-safety-tips"></a>Trabajar con sugerencias de seguridad

Los administradores pueden activar o desactivar las sugerencias de seguridad en las directivas contra correo no deseado. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).

Si no está de acuerdo con cómo EOP clasificó un mensaje (es decir, el mensaje no es correo no deseado o debería haber sido marcado como correo no deseado), puede enviar los mensajes a Microsoft para su análisis para ayudarle a mejorar su experiencia. Para obtener instrucciones, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md). También puede hacer clic en el vínculo Comentarios de la sugerencia de seguridad para enviar comentarios directamente a Microsoft para ayudarnos a mejorar.
