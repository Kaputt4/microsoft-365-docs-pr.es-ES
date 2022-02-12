---
title: Enviar correo electrónico cifrado
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Obtenga información sobre cómo enviar correo electrónico cifrado Outlook.
ms.openlocfilehash: 15f5b87fb238d4a872f13c11f1e88892f628a255
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "62768058"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Cifre o etiquete su correo electrónico confidencial

Los datos y la información de la campaña son importantes y, a menudo, confidenciales. Ayude a proteger esta información confidencial mediante el uso de etiquetas de cifrado y confidencialidad para que usted y los destinatarios de correo electrónico traten la información con la confidencialidad que requiere.

## <a name="best-practices"></a>Procedimientos recomendados

Antes de enviar correo electrónico con información confidencial o confidencial, considere la posibilidad de activar:

- **Cifrado:** Puede cifrar el correo electrónico para proteger la privacidad de la información del correo electrónico. Al cifrar un mensaje de correo electrónico, se convierte de texto sin formato legible en texto de chipher codificado. Solo el destinatario que tiene la clave privada que coincide con la clave pública usada para cifrar el mensaje puede descifrar el mensaje para su lectura. Sin embargo, cualquier destinatario sin la clave privada correspondiente ve texto indescifrable. El administrador puede definir reglas para cifrar automáticamente los mensajes que cumplan determinados criterios. Por ejemplo, el administrador puede crear una regla que cifre todos los mensajes enviados fuera de la organización o todos los mensajes que mencionen palabras o frases específicas. Las reglas de cifrado se aplicarán automáticamente.
- **Etiquetas de confidencialidad:** Tu campaña también puede configurar etiquetas de confidencialidad que puedes aplicar a tus archivos y correo electrónico para que cumplan con las directivas de protección de la información de la campaña. Al establecer una etiqueta, la etiqueta persiste con el correo electrónico, incluso cuando se envía; por ejemplo, aparece como un encabezado en el mensaje.

![Diagrama de un correo electrónico con llamadas para etiquetas y cifrado.](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>Configúrelo

Si desea cifrar un mensaje que no cumple con una regla predefinida o el administrador no ha configurado ninguna regla, puede aplicar una variedad de reglas de cifrado diferentes antes de enviar el mensaje. Para enviar un mensaje cifrado desde Outlook 2013 o 2016, o Outlook 2016 para Mac, seleccione Opciones **> permisos** y, a continuación, seleccione la opción de protección que necesita. También puede enviar un mensaje cifrado seleccionando el botón **Proteger** en Outlook en la Web. Para obtener más información, vea [Enviar, ver y responder a mensajes cifrados en Outlook para PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="admin-settings"></a>Configuración de administrador

Puede obtener información sobre cómo configurar el cifrado de correo electrónico en [el cifrado de correo electrónico en Microsoft 365](../compliance/email-encryption.md).

### <a name="automatically-encrypt-email-messages"></a>Cifrar automáticamente mensajes de correo electrónico

Los administradores pueden crear reglas de flujo de correo para proteger automáticamente los mensajes de correo electrónico que se envían y reciben de la campaña. Configure reglas para cifrar los mensajes de correo electrónico salientes y quite el cifrado de los mensajes cifrados procedentes de dentro de la organización o de las respuestas a los mensajes cifrados enviados desde su organización.

Se crean reglas de flujo de correo para cifrar los mensajes de correo electrónico con las nuevas Cifrado de mensajes de Office 365 (OME). Defina reglas de flujo de correo para desencadenar el cifrado de mensajes con las nuevas funcionalidades de OME mediante <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">el Exchange de administración (EAC)</a>. 

1. En un explorador web, con una cuenta de trabajo o escuela a la que se han concedido permisos de administrador global, inicie sesión.
2. Elija el icono Administrador.
3. En el Centro de administración, elija **Centros de administración > Exchange**.

Para obtener más información, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico](../compliance/define-mail-flow-rules-to-encrypt-email.md).

### <a name="brand-your-encryption-messages"></a>Marca los mensajes de cifrado

También puedes aplicar la personalización de marca de la campaña para personalizar la apariencia y el texto de los mensajes de correo electrónico. Para obtener más información, [consulta Agregar la marca de la organización a los mensajes cifrados](../compliance/email-encryption.md).