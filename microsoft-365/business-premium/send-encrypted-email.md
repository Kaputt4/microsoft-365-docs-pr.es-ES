---
title: Enviar correo electrónico cifrado
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
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
description: Obtenga información sobre cómo enviar un correo electrónico cifrado mediante Outlook.
ms.openlocfilehash: e4a25cc59d0d92c1905507b1e5db1253f120849c
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66489566"
---
# <a name="encrypt-or-label-your-sensitive-email-in-microsoft-365"></a>Cifrar o etiquetar el correo electrónico confidencial en Microsoft 365

Los datos y la información son importantes y, a menudo, confidenciales. El objetivo es ayudar a proteger esta información confidencial asegurándose de que todos usen etiquetas de confidencialidad para que los destinatarios del correo electrónico traten la información con la máxima confidencialidad.

## <a name="best-practices"></a>Procedimientos recomendados

Antes de que las personas envíen un correo electrónico con información confidencial o sensible, deben considerar la posibilidad de activar:

- **Cifrado:** Puede cifrar su correo electrónico para proteger la privacidad de la información en el correo electrónico. Al cifrar un mensaje de correo electrónico, se convierte de texto sin formato legible en texto cifrado codificado. Solo el destinatario que tenga la clave privada que coincida con la clave pública usada para cifrar el mensaje puede descifrar el mensaje para su lectura. Sin embargo, cualquier destinatario sin la clave privada correspondiente ve un texto indescifrable. El administrador puede definir reglas para cifrar automáticamente los mensajes que cumplen determinados criterios. Por ejemplo, el administrador puede crear una regla que cifre todos los mensajes enviados fuera de la organización o todos los mensajes que mencionen palabras o frases específicas. Las reglas de cifrado se aplicarán automáticamente.

- **Etiquetas de confidencialidad:** Si su organización lo requiere, puede configurar etiquetas de confidencialidad que aplique a los archivos y al correo electrónico para que cumplan las directivas de protección de la información de su organización. Al establecer una etiqueta, la etiqueta se conserva con el correo electrónico, incluso cuando se envía &mdash;, por ejemplo, apareciendo como un encabezado del mensaje.

![Diagrama de un correo electrónico con llamadas para etiquetas y cifrado.](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>Configúrelo

Si desea cifrar un mensaje que no cumple una regla predefinida o el administrador no ha configurado ninguna regla, puede aplicar una variedad de reglas de cifrado diferentes antes de enviar el mensaje. Para enviar un mensaje cifrado desde Outlook 2013 o 2016, o Outlook 2016 para Mac, seleccione **Opciones > Permisos** y, a continuación, seleccione la opción de protección que necesita. También puede enviar un mensaje cifrado al seleccionar el botón **Proteger** en Outlook en la web. Para obtener más información, consulte [Enviar, ver y responder a mensajes cifrados en Outlook para PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="admin-settings"></a>Configuración de administrador

Puede obtener información sobre cómo configurar el cifrado de correo electrónico en [Cifrado de correo electrónico en Microsoft 365](../compliance/email-encryption.md).

### <a name="automatically-encrypt-email-messages"></a>Cifrar automáticamente los mensajes de correo electrónico

Los administradores pueden crear reglas de flujo de correo para proteger automáticamente los mensajes de correo electrónico que se envían y reciben de una campaña o empresa. Configure reglas para cifrar los mensajes de correo electrónico salientes y eliminar el cifrado de los mensajes cifrados procedentes de su organización o de respuestas a mensajes cifrados enviados desde su organización.

Cree reglas de flujo de correo para cifrar los mensajes de correo electrónico con Cifrado de mensajes de Microsoft Purview. Defina reglas de flujo de correo para desencadenar el cifrado de mensajes mediante el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange (EAC)</a>.

1. Inicie sesión en un explorador web con una cuenta profesional o educativa a la que se hayan concedido permisos de administrador global.
2. Elija el icono Administrador.
3. En el Centro de administración, elija **Centros de administración > Exchange**.

Para obtener más información, consulte [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico](../compliance/define-mail-flow-rules-to-encrypt-email.md).

### <a name="brand-your-encryption-messages"></a>Personalice los mensajes de cifrado

También puede aplicar la personalización para personalizar la apariencia y el texto de los mensajes de correo electrónico. Para obtener más información, consulte [Agregar la marca de su organización a los mensajes cifrados](../compliance/email-encryption.md).

## <a name="next-mission"></a>Próxima misión

Si ha llegado hasta aquí, ha completado correctamente otra misión, así que ¡felicitaciones! No hay tiempo para descansar en nuestros éxitos, así que comencemos a configurar un entorno seguro en el que el equipo pueda [colaborar de forma segura](m365bp-collaborate-share-securely.md).