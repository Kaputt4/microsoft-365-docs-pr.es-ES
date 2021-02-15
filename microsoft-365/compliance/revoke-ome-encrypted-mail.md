---
title: Revocar el correo electrónico cifrado mediante el cifrado avanzado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Como administrador y como remitente de mensajes, puede revocar ciertos correos electrónicos cifrados con cifrado de mensajes avanzado de Office 365.
ms.openlocfilehash: 67582917dd483f6090f5cd369af8faf6cf8a4ea8
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105145"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Revocar el correo electrónico cifrado mediante el cifrado avanzado de mensajes

La revocación de correo electrónico se ofrece como parte del cifrado avanzado de mensajes de Office 365. El cifrado avanzado de mensajes de Office 365 se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precios para el personal sin ánimo de lucro), Office 365 Enterprise E5 (precios de personal para ong) y Office 365 Educación A5. Si su organización tiene una suscripción que no incluye el cifrado avanzado de mensajes de Office 365, puede comprarla con el complemento SKU de cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios para el personal sin ánimo de lucro) o el complemento SKU de cumplimiento avanzado de Office 365 para Microsoft 365 E3, Microsoft 365 E3 (precios de personal para ong) u SKU de Office 365.

Este artículo forma parte de una serie más amplia de artículos sobre el cifrado de mensajes de [Office 365.](ome.md)

Si un mensaje se ha cifrado mediante el cifrado avanzado de mensajes de Office 365 y es administrador de Microsoft 365 o es el remitente del mensaje, puede revocar el mensaje en determinadas condiciones. Los administradores revocan mensajes con PowerShell. Como remitente, revoca un mensaje que envió directamente desde Outlook en la Web. En este artículo se describen las circunstancias en las que la revocación es posible y cómo hacerlo.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Mensajes de correo electrónico cifrados que puede revocar

Los administradores y remitentes de mensajes pueden revocar correos electrónicos cifrados si el destinatario ha recibido un correo electrónico cifrado basado en vínculos con marca. Si el destinatario recibió una experiencia en línea nativa en un cliente de Outlook compatible, no puede revocar el mensaje.

El hecho de que un destinatario reciba una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: los destinatarios de office 365 y la cuenta microsoft (por ejemplo, los usuarios de outlook.com) obtienen una experiencia en línea en los clientes de Outlook compatibles. Todos los demás tipos de destinatarios, como los destinatarios de Gmail y Yahoo, obtienen una experiencia basada en vínculos.

Los administradores y remitentes de mensajes pueden revocar mensajes cifrados mediante el cifrado aplicado directamente desde Outlook en la Web. Por ejemplo, los mensajes cifrados con la opción Cifrar solo.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Captura de pantalla que muestra la opción Cifrar solo en Outlook en la Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Experiencia del destinatario para mensajes de correo electrónico cifrados revocados

Una vez que se ha revocado un correo electrónico, el destinatario recibe un error cuando accede al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "El remitente ha revocado el mensaje".

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Cómo revocar un mensaje cifrado que envió

Puede revocar un correo que envió a un único destinatario que usa una cuenta social como gmail.com o yahoo.com. En otras palabras, puede revocar un correo electrónico enviado a un único destinatario que recibió la experiencia basada en vínculos.

No puede revocar un correo que envió a un destinatario que usa una cuenta de Office 365 o Microsoft 365 o un usuario que usa una cuenta de Microsoft, por ejemplo, una cuenta outlook.com educativa. 

Para revocar un mensaje cifrado que ha enviado, siga estos pasos

1. En Outlook en la Web, en la **carpeta Enviado,** vaya al mensaje que desea revocar.

   Si el correo es revocable, verá el vínculo "Quitar acceso externo" en la parte superior del mensaje.

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Captura de pantalla que muestra el correo cifrado que desea revocar en Outlook en la Web.":::

2. Haga **clic en Quitar acceso externo** para revocar el mensaje.

   El mensaje muestra que su estado está revocado.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Captura de pantalla que muestra un mensaje cifrado revocado en Outlook en la Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>Cómo revocar un mensaje cifrado como administrador

Los administradores de Microsoft 365 siguen estos pasos generales para revocar un correo electrónico cifrado apto:

- Obtenga el id. de mensaje del correo electrónico.
- Compruebe que puede revocar el mensaje.
- Revocar el correo.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Paso 1. Obtener el id. de mensaje del correo electrónico

Antes de poder revocar un correo cifrado, recopilo el id. de mensaje del correo. El MessageId suele tener el formato:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Hay varias formas de encontrar el id. de mensaje del correo electrónico que desea revocar. En esta sección se describen un par de opciones, pero puede usar cualquier método que proporciona el identificador.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Para identificar el id. de mensaje del correo electrónico que desea revocar mediante seguimiento de mensajes en el Centro de &amp; cumplimiento de seguridad

1. Busque el correo electrónico por remitente o destinatario mediante Nuevo seguimiento de mensajes en [el Centro de & cumplimiento.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)

2. Una vez que haya encontrado el correo electrónico, selecciónelo para abrir el panel de detalles de **seguimiento de** mensajes. Expanda **Más información para** buscar el id. de mensaje.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante los informes de cifrado de mensajes de Office en el Centro de &amp; cumplimiento de seguridad

1. En el Centro &amp; de cumplimiento de seguridad, vaya al informe **de cifrado de mensajes.** Para obtener información sobre este informe, vea [Ver informes de seguridad de correo electrónico en el Centro de cumplimiento de &amp; seguridad.](../security/office-365-security/view-email-security-reports.md)

2. Elija la **tabla Ver detalles** e identifique el mensaje que desea revocar.

3. Haga doble clic en el mensaje para ver los detalles que incluyen el id. de mensaje.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Paso 2. Comprobar que el correo es revocable

Para comprobar si puede revocar un mensaje, compruebe si el campo Estado  de revocación está visible en el informe de cifrado, en la tabla Detalles del Centro de &amp; cumplimiento de seguridad.

Para comprobar si puede revocar un mensaje de correo electrónico determinado mediante Windows PowerShell, siga estos pasos.

1. Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, inicie una sesión Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el Get-OMEMessageStatus cmdlet de la siguiente manera:

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

Una vez que conozca el id. de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico mediante el Centro de cumplimiento de seguridad &amp; o Windows PowerShell.

Para revocar el mensaje mediante el Centro de &amp; cumplimiento de seguridad

1. Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese al Centro de & cumplimiento.

2. En el **informe cifrado**, en la **tabla Detalles** del mensaje, elija Revocar **mensaje**.

Para revocar un correo electrónico mediante Windows PowerShell, use el cmdlet Set-OMEMessageRevocation.

1. Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell.](https://aka.ms/exopowershell)

2. Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Para comprobar si se revocó el correo electrónico, ejecute el cmdlet Get-OMEMessageStatus siguiente:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Si la revocación se ha realizado correctamente, el cmdlet devuelve el siguiente resultado:  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Más información sobre el cifrado avanzado de mensajes de Office 365

- [Cifrado avanzado de mensajes de Office 365](ome-advanced-message-encryption.md)

- [Cifrado de mensajes avanzado de Office 365: expiración del correo electrónico](ome-advanced-expiration.md)

- [Descripción del servicio de cumplimiento y directiva de mensajes](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
