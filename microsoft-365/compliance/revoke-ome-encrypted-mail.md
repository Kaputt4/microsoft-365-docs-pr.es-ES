---
title: Revocar correo electrónico cifrado por el cifrado de mensajes avanzado
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
description: Como administrador y como remitente del mensaje, puede revocar determinados mensajes de correo electrónico cifrados con el cifrado de mensajes avanzado de Office 365.
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868964"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Revocar correo electrónico cifrado por el cifrado de mensajes avanzado

La revocación de correo electrónico se ofrece como parte de un cifrado de mensajes avanzado de Office 365. Office 365 Advanced Message Encryption se incluye en [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precio de personal sin ánimo de lucro), Office 365 Enterprise E5 (precio de personal sin ánimo de lucro) y Office 365 Education A5. Si su organización tiene una suscripción que no incluye el cifrado avanzado de mensajes de Office 365, puede adquirirlo con el complemento de SKU de cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios para trabajadores sin ánimo de lucro), o el complemento de SKU de Office 365 Advanced Compliance para Microsoft 365 E3, Microsoft 365 E3 (no lucrativa personal) u Office 365 SKU.

Este artículo forma parte de una amplia serie de artículos sobre el [cifrado de mensajes de Office 365](ome.md).

Si un mensaje se cifró mediante el cifrado de mensajes avanzado de Office 365 y es administrador de Microsoft 365 o usted es el remitente del mensaje, puede revocar el mensaje en determinadas condiciones. Los administradores revocan los mensajes con PowerShell. Como remitente, revoca un mensaje que envió directamente desde Outlook en la Web. En este artículo se describen las circunstancias en las que es posible la revocación y cómo hacerlo.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Mensajes de correo electrónico cifrados que puede revocar

Los administradores y los remitentes de mensajes pueden revocar correos electrónicos cifrados si el destinatario recibe un correo electrónico cifrado basado en vínculos y con marcas. Si el destinatario recibe una experiencia en línea nativa en un cliente de Outlook compatible, no podrá revocar el mensaje.

El hecho de que un destinatario reciba una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: Office 365 y los destinatarios de la cuenta de Microsoft (por ejemplo, usuarios outlook.com) obtienen una experiencia en línea en clientes de Outlook compatibles. Todos los demás tipos de destinatarios, como los destinatarios de gmail y Yahoo, obtienen una experiencia basada en vínculos.

Los administradores y los remitentes de mensajes pueden revocar mensajes cifrados mediante el cifrado que se aplican directamente desde Outlook en la Web. Por ejemplo, los mensajes cifrados con la opción solo cifrar.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Captura de pantalla que muestra la opción solo cifrar en Outlook en la Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Experiencia del destinatario para correos electrónicos cifrados revocados

Una vez que se ha revocado un correo electrónico, el destinatario recibe un error cuando accede al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "el remitente ha revocado el mensaje".

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Cómo revocar un mensaje cifrado que envió

Para revocar un mensaje cifrado que envió, siga estos pasos

1. En Outlook en la web, en la carpeta **enviados** , busque el mensaje que desea revocar.

   Si el correo es revocable, verá el vínculo "Quitar acceso externo" en la parte superior del mensaje.

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Captura de pantalla que muestra el correo cifrado que desea revocar en Outlook en la Web.":::

2. Haga clic en **Quitar acceso externo** para revocar el mensaje.

   El mensaje muestra que su estado es revocado.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Captura de pantalla que muestra el mensaje cifrado revocado en Outlook en la Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>Cómo revocar un mensaje cifrado como administrador

Los administradores de Microsoft 365 siguen estos pasos generales para revocar un correo electrónico cifrado apto:

- Obtenga el identificador de mensaje del correo electrónico.
- Compruebe que puede revocar el mensaje.
- Revocar el correo.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Paso 1. Obtener el identificador del mensaje de correo electrónico

Para poder revocar un correo cifrado, reúna el identificador de mensaje del correo. El MessageId suele tener el formato:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Hay varias formas de buscar el identificador de mensaje del correo electrónico que desea revocar. En esta sección se describen un par de opciones, pero puede usar cualquier método que proporcione el ID.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante el seguimiento de mensajes en el centro de seguridad y &amp; cumplimiento

1. Busque el correo electrónico por remitente o destinatario mediante el [seguimiento de mensajes nuevos en el centro de seguridad & cumplimiento](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).

2. Una vez que haya encontrado el correo electrónico, selecciónelo para que aparezca el panel de **detalles de seguimiento de mensajes** . Expanda **más información** para buscar el identificador de mensaje.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante los informes de cifrado de mensajes de Office en el centro de seguridad y &amp; cumplimiento

1. En el centro de seguridad &amp; y cumplimiento, navegue hasta el **Informe de cifrado de mensajes**. Para obtener información sobre este informe, consulte [ver informes de seguridad de correo electrónico en el centro de seguridad y &amp; cumplimiento](../security/office-365-security/view-email-security-reports.md).

2. Elija la tabla **Ver detalles** e identifique el mensaje que desea revocar.

3. Haga doble clic en el mensaje para ver los detalles que incluyen el identificador del mensaje.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Paso 2. Comprobar que el correo es revocable

Para comprobar si puede revocar un mensaje, compruebe si el campo Estado de revocación está visible en el informe de cifrado, en la tabla de **detalles** del centro de seguridad y &amp; cumplimiento.

Para comprobar si puede revocar un mensaje de correo electrónico determinado mediante Windows PowerShell, siga estos pasos.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Este comando devuelve el asunto del mensaje y si el mensaje es revocable. Por ejemplo,

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>Paso 3. Revocar el correo

Una vez que conozca el identificador de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico mediante el centro de seguridad y &amp; cumplimiento o Windows PowerShell.

Para revocar el mensaje mediante el centro de seguridad y &amp; cumplimiento

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, conéctese al centro de seguridad & cumplimiento.

2. En el **Informe de cifrado**, en la tabla de **detalles** del mensaje, elija **revocar mensaje**.

Para revocar un correo electrónico mediante Windows PowerShell, use el cmdlet Set-OMEMessageRevocation.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [Conéctese a PowerShell de Exchange Online](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Para comprobar si el correo electrónico se ha revocado, ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Si la revocación se ha realizado correctamente, el cmdlet devuelve el siguiente resultado:  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Más información sobre el cifrado de mensajes avanzado de Office 365

- [Cifrado avanzado de mensajes de Office 365](ome-advanced-message-encryption.md)

- [Office 365 Advanced Message Encryption-expiración del correo electrónico](ome-advanced-expiration.md)

- [Descripción de la Directiva de mensajes y el servicio de cumplimiento](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
