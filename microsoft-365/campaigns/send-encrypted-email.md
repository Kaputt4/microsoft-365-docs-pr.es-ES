---
title: Enviar correo electrónico cifrado
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Obtenga información sobre cómo enviar correo electrónico cifrado mediante Outlook.
ms.openlocfilehash: e7028f69f4418ae0ff0183653c509fc9ad6171ac
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031235"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Cifrar o etiquetar el correo electrónico confidencial

Los datos y la información de la campaña son importantes y, a menudo, confidenciales. Ayude a proteger esta información confidencial mediante el cifrado y las etiquetas de confidencialidad para que usted y los destinatarios del correo electrónico traten la información con la confidencialidad que necesita.


## <a name="best-practices"></a>Procedimientos recomendados

Antes de enviar mensajes de correo electrónico con información confidencial o confidencial, considere la posibilidad de activar:

- **Cifrado:** Puede cifrar el correo electrónico para proteger la privacidad de la información del correo electrónico. Al cifrar un mensaje de correo electrónico, se convierte de texto sin formato legible en texto cifrado recodificado. Solo el destinatario que tiene la clave privada que coincide con la clave pública que se usa para cifrar el mensaje puede descifrar el mensaje para leerlo. Sin embargo, los destinatarios que no tengan la clave privada correspondiente verán el texto indescifrable. El administrador puede definir reglas para cifrar automáticamente los mensajes que cumplan determinados criterios. Por ejemplo, el administrador puede crear una regla que cifre todos los mensajes enviados fuera de la organización o todos los mensajes que mencionen palabras o frases específicas. Las reglas de cifrado se aplicarán automáticamente.
- **Etiquetas de confidencialidad:** La campaña también puede configurar las etiquetas de confidencialidad que puede aplicar a sus archivos y correo electrónico para mantenerlos conformes con las directivas de protección de la información de la campaña. Cuando se establece una etiqueta, la etiqueta persiste con el correo electrónico, incluso cuando se envía, por ejemplo, al aparecer como encabezado del mensaje.

![Diagrama de un correo electrónico con llamadas para etiquetas y cifrado](media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>Configúrelo

Si desea cifrar un mensaje que no cumple una regla predefinida o el administrador no ha configurado ninguna regla, puede aplicar una variedad de reglas de cifrado distintas antes de enviar el mensaje. Para enviar un mensaje cifrado desde Outlook 2013 o 2016 o Outlook 2016 para Mac, seleccione **opciones > permisos**y, a continuación, seleccione la opción de protección que necesite. También puede enviar un mensaje cifrado seleccionando el botón **proteger** en Outlook en la Web. Para obtener más información, vea [enviar, ver y responder a mensajes cifrados en Outlook para PC](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US).

## <a name="admin-settings"></a>Configuración de administración

Puede obtener información sobre cómo configurar el cifrado de correo electrónico en [cifrado de correo electrónico en Office 365](https://docs.microsoft.com/office365/securitycompliance/email-encryption).

### <a name="automatically-encrypt-email-messages"></a>Cifrar mensajes de correo automáticamente

Los administradores pueden crear reglas de flujo de correo para proteger automáticamente los mensajes de correo electrónico que se envían y reciben desde la campaña. Configure las reglas para cifrar los mensajes de correo electrónico salientes y quite el cifrado de los mensajes cifrados que provengan de la organización o de las respuestas a los mensajes cifrados que se envían desde la organización. 

Puede crear reglas de flujo de correo para cifrar los mensajes de correo electrónico con las nuevas capacidades de cifrado de mensajes de Office 365 (OME). Definir reglas de flujo de correo para desencadenar el cifrado de mensajes con las nuevas capacidades de OME mediante el centro de administración de Exchange (EAC). 

1. En un explorador Web, con una cuenta profesional o educativa a la que se le han concedido permisos de administrador global, inicie sesión en Office 365. 
2. Elija el icono administración. 
3. En el centro de administración, elija **centros de administración > Exchange**. 

Para obtener más información, vea [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](https://docs.microsoft.com/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).

### <a name="brand-your-encryption-messages"></a>Marcar los mensajes de cifrado

También puede aplicar la personalización de marca de la campaña para personalizar la apariencia y el texto de los mensajes de correo electrónico. Para obtener más información, vea [Agregar la marca de la organización a los mensajes cifrados](https://docs.microsoft.com/office365/securitycompliance/email-encryption).

