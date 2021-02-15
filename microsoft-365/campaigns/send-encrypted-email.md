---
title: Enviar correo electrónico cifrado
f1.keywords:
- NOCSH
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
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Obtenga información sobre cómo enviar correo electrónico cifrado con Outlook.
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044221"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Cifre o etiquete su correo electrónico confidencial

Los datos y la información de la campaña son importantes y suelen ser confidenciales. Ayude a proteger esta información confidencial mediante el cifrado y las etiquetas de confidencialidad para que usted y sus destinatarios de correo electrónico traten la información con la confidencialidad que requiere.

## <a name="best-practices"></a>Procedimientos recomendados

Antes de enviar correo electrónico con información confidencial, considere la posibilidad de activar:

- **Cifrado:** Puede cifrar el correo electrónico para proteger la privacidad de la información del correo electrónico. Cuando se cifra un mensaje de correo electrónico, se convierte de texto sin formato legible en texto desenlazado. Solo el destinatario que tiene la clave privada que coincide con la clave pública usada para cifrar el mensaje puede descifrarlo para leerlo. Sin embargo, cualquier destinatario sin la clave privada correspondiente ve texto indescifrable. El administrador puede definir reglas para cifrar automáticamente los mensajes que cumplen ciertos criterios. Por ejemplo, el administrador puede crear una regla que cifre todos los mensajes enviados fuera de la organización o todos los mensajes que mencionen palabras o frases específicas. Las reglas de cifrado se aplicarán automáticamente.
- **Etiquetas de confidencialidad:** Tu campaña también puede configurar etiquetas de confidencialidad que puedes aplicar a tus archivos y correo electrónico para que cumplan las directivas de protección de la información de tu campaña. Cuando se establece una etiqueta, la etiqueta persiste con el correo electrónico, incluso cuando se envía, por ejemplo, al aparecer como un encabezado en el mensaje.

![Diagrama de un correo electrónico con llamadas para etiquetas y cifrado](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>Configúrelo

Si desea cifrar un mensaje que no cumple una regla predefinida o su administrador no ha configurado ninguna regla, puede aplicar una variedad de reglas de cifrado diferentes antes de enviar el mensaje. Para enviar un mensaje cifrado desde Outlook 2013 o 2016, o Outlook 2016 para Mac, seleccione Opciones **> Permisos** y, a continuación, seleccione la opción de protección que necesita. También puede enviar un mensaje cifrado seleccionando el botón **Proteger** en Outlook en la Web. Para obtener más información, vea Enviar, ver y responder a mensajes [cifrados en Outlook para PC.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="admin-settings"></a>Configuración de administrador

Puede obtener información sobre cómo configurar el cifrado de correo electrónico en el cifrado [de correo electrónico en Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)

### <a name="automatically-encrypt-email-messages"></a>Cifrar automáticamente los mensajes de correo electrónico

Los administradores pueden crear reglas de flujo de correo para proteger automáticamente los mensajes de correo electrónico que se envían y reciben de la campaña. Configure reglas para cifrar los mensajes de correo electrónico saliente y quitar el cifrado de los mensajes cifrados procedentes de su organización o de las respuestas a los mensajes cifrados enviados desde su organización.

Cree reglas de flujo de correo para cifrar mensajes de correo electrónico con las nuevas capacidades de Cifrado de mensajes de Office 365 (OME). Definir reglas de flujo de correo para desencadenar el cifrado de mensajes con las nuevas funcionalidades de OME mediante el Centro de administración de Exchange (EAC). 

1. En un explorador web, con una cuenta de trabajo o escuela a la que se hayan concedido permisos de administrador global, inicie sesión.
2. Elija el icono Administrador.
3. En el centro de administración, elija **Centros de administración > Exchange**.

Para obtener más información, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico.](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

### <a name="brand-your-encryption-messages"></a>Personal de marca de los mensajes de cifrado

También puedes aplicar la personalización de marca de la campaña para personalizar el aspecto y el texto de los mensajes de correo electrónico. Para obtener más información, [vea Agregar la marca de su organización a los mensajes cifrados.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)
