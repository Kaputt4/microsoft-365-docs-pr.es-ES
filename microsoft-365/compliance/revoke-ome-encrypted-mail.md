---
title: Revocar el correo electrónico cifrado por cifrado de mensajes avanzado
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 03/04/2022
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Como administrador y como remitente de mensajes, puede revocar ciertos correos electrónicos cifrados con Cifrado de mensajes avanzado de Office 365.
ms.openlocfilehash: bf793dce23c91e8b45f96114e6c4a56c866adc32
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "63512258"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Revocar el correo electrónico cifrado por cifrado de mensajes avanzado

La revocación de correo electrónico se ofrece como parte de Cifrado de mensajes avanzado de Office 365. Cifrado de mensajes avanzado de Office 365 se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precios de personal sin ánimo de lucro), Office 365 Enterprise  E5 (precios de personal sin ánimo de lucro) y Office 365 Educación A5. Si su organización tiene una suscripción que no incluye Cifrado de mensajes avanzado de Office 365, puede comprarla con el complemento SKU de Cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3  (Precios de personal sin ánimo de lucro) o el complemento sku Cumplimiento avanzado de Office 365 para Microsoft 365 E3, Microsoft 365 E3 (precios de personal sin ánimo de lucro) o Office 365 SKU.

Este artículo forma parte de una serie más grande de artículos sobre [Cifrado de mensajes de Office 365](ome.md).

Si un mensaje se cifra mediante Cifrado de mensajes avanzado de Office 365 y es un administrador de Microsoft 365 o es el remitente del mensaje, puede revocar el mensaje en determinadas condiciones. Los administradores revocan los mensajes con PowerShell. Como remitente, revoca un mensaje que envió directamente desde Outlook en la Web. En este artículo se describen las circunstancias en las que es posible la revocación y cómo hacerlo.

> [!NOTE]
> Para garantizar que la capacidad de realizar un seguimiento y revocar mensajes de OME está disponible, debe agregar una plantilla de personalización de marca personalizada. Consulta [Agregar la marca de la organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Correos electrónicos cifrados que puede revocar

Los administradores y los remitentes de mensajes pueden revocar los correos electrónicos cifrados si el destinatario recibió un correo electrónico cifrado basado en vínculos con marca. Si el destinatario recibió una experiencia en línea nativa en un cliente Outlook, no puede revocar el mensaje.

Si un destinatario recibe una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: los destinatarios de cuentas de Office 365 y Microsoft (por ejemplo, usuarios de outlook.com) obtienen una experiencia en línea en clientes Outlook compatibles. Todos los demás tipos de destinatarios, como los destinatarios de Gmail y Yahoo, obtienen una experiencia basada en vínculos.

Los administradores y remitentes de mensajes pueden revocar los mensajes cifrados mediante el cifrado aplicado directamente desde Outlook en la Web. Por ejemplo, los mensajes cifrados con la opción Cifrar solo.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Captura de pantalla que muestra la opción Cifrar solo en Outlook en la Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Experiencia de destinatarios para correos electrónicos cifrados revocados

Una vez revocado un correo electrónico, el destinatario recibe un error cuando accede al correo electrónico cifrado a través del portal de Cifrado de mensajes de Office 365: "El remitente ha revocado el mensaje".

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Cómo revocar un mensaje cifrado que envió

Puede revocar un correo que envió a un único destinatario que usa una cuenta social como gmail.com o yahoo.com. En otras palabras, puede revocar un correo electrónico enviado a un único destinatario que recibió la experiencia basada en vínculos.

No puede revocar un correo que envió a un destinatario que usa una cuenta de trabajo o educativa de Office 365 o Microsoft 365 o un usuario que usa una cuenta de Microsoft, por ejemplo, una cuenta outlook.com. 

Para revocar un mensaje cifrado que envió, siga estos pasos

1. En Outlook en la Web, en la **carpeta Enviado**, vaya al mensaje que desea revocar.

   Si el correo es revocable, verá el vínculo "Quitar acceso externo" en la parte superior del mensaje.

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Captura de pantalla que muestra el correo cifrado que desea revocar en Outlook en la Web.":::

2. Haga **clic en Quitar acceso externo** para revocar el mensaje.

   El mensaje muestra que su estado se revoca.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Captura de pantalla que muestra un mensaje cifrado revocado Outlook en la Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>Cómo revocar un mensaje cifrado como administrador

Microsoft 365 los administradores siguen estos pasos generales para revocar un correo electrónico cifrado elegible:

- Obtener el identificador de mensaje del correo electrónico.
- Compruebe que puede revocar el mensaje.
- Revocar el correo.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Paso 1. Obtener el identificador de mensaje del correo electrónico

Antes de poder revocar un correo cifrado, recopilo el identificador de mensaje del correo. MessageId suele tener el formato:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Hay varias maneras de buscar el identificador de mensaje del correo electrónico que desea revocar. En esta sección se describen un par de opciones, pero puede usar cualquier método que proporciona el identificador.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante el seguimiento de mensajes en el Centro de cumplimiento &amp; de seguridad

1. Busque el correo electrónico por remitente o destinatario mediante Nuevo seguimiento de mensajes en [el Centro de & cumplimiento](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).

2. Una vez que haya localizado el correo electrónico, selecciónelo para que se active el panel **Detalles del seguimiento de** mensajes. Expanda **Más información para** buscar el identificador de mensaje.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante Office de cifrado de mensajes en el Centro de &amp; cumplimiento de seguridad

1. En el Centro de &amp; seguridad y cumplimiento, vaya al informe **de cifrado de mensajes**. Para obtener información sobre este informe, vea [Ver informes de seguridad de correo electrónico en el Centro de &amp; cumplimiento de seguridad](../security/office-365-security/view-email-security-reports.md).

2. Elija la **tabla Ver detalles** e identifique el mensaje que desea revocar.

3. Haga doble clic en el mensaje para ver los detalles que incluyen el identificador de mensaje.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Paso 2. Comprobar que el correo es revocable

Para comprobar si puede revocar un mensaje, compruebe si el campo Estado de revocación está visible en el informe cifrado, en la  tabla Detalles del Centro de &amp; cumplimiento de seguridad.

Para comprobar si puede revocar un mensaje de correo electrónico determinado mediante Windows PowerShell, siga estos pasos.

1. Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Este comando devuelve el asunto del mensaje y si el mensaje es revocable. Por ejemplo,

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>Paso 3. Revocar el correo

Una vez que conozca el identificador de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, &amp; puede revocar el correo electrónico mediante el Centro de cumplimiento de seguridad o Windows PowerShell.

Para revocar el mensaje mediante el Centro de cumplimiento &amp; de seguridad

1. Con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, conéctese al Centro de seguridad & cumplimiento.

2. En el **informe Cifrado**, en la **tabla Detalles** del mensaje, elija **Revocar mensaje**.

Para revocar un correo electrónico mediante Windows PowerShell, use el cmdlet Set-OMEMessageRevocation.

1. Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, Conectar [para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Para comprobar si el correo electrónico se revocó, ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Si la revocación se ha realizado correctamente, el cmdlet devuelve el siguiente resultado:  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Más información sobre Cifrado de mensajes avanzado de Office 365

- [Cifrado avanzado de mensajes de Office 365](ome-advanced-message-encryption.md)

- [Cifrado de mensajes avanzado de Office 365: expiración de correo electrónico](ome-advanced-expiration.md)

- [Descripción del servicio de cumplimiento y directiva de mensajes](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)