---
title: Revocación del correo electrónico cifrado mediante cifrado avanzado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 05/02/2022
ms.collection:
- tier1
- purview-compliance
search.appverid:
- MET150
description: Como administrador y como remitente de mensajes, puede revocar determinados correos electrónicos cifrados con cifrado avanzado de mensajes de Microsoft Purview.
ms.openlocfilehash: bdae122260b932111017b1a0af31bb268d46a9d6
ms.sourcegitcommit: a88aadf5786f1bd9e5bae763f603a2b690473322
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68817459"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Revocación del correo electrónico cifrado mediante cifrado avanzado de mensajes

Email revocación se ofrece como parte del cifrado avanzado de mensajes de Microsoft Purview. El cifrado avanzado de mensajes de Microsoft Purview se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precios del personal sin ánimo de lucro), Office 365 Enterprise E5 (precios del personal sin ánimo de lucro) y Office 365 Educación A5. Para usar las funciones de revocación y expiración de Advanced Message Encryption, habilite la opción **Cifrado Premium en Office 365** en la licencia de E5.

Si su organización tiene una suscripción que no incluye el cifrado avanzado de mensajes de Microsoft Purview, puede comprarlo con el complemento de SKU de Cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios del personal sin ánimo de lucro) o el Cumplimiento avanzado de Office 365 complemento de SKU para Microsoft 365 E3, Microsoft 365 E3 (precios del personal sin ánimo de lucro) o SKU de Office 365.

Este artículo forma parte de una serie más amplia de artículos sobre [Office 365 cifrado de mensajes](ome.md).

Si un mensaje se cifró mediante cifrado avanzado de mensajes de Microsoft Purview y es administrador de Microsoft 365 o es el remitente del mensaje, puede revocarlo en determinadas condiciones. Los administradores revocan mensajes mediante PowerShell. Como remitente, revoca un mensaje que envió directamente desde Outlook en la Web. En este artículo se describen las circunstancias en las que es posible la revocación y cómo hacerlo.

> [!NOTE]
> Para garantizar que la capacidad de realizar un seguimiento y revocar mensajes OME está disponible, debe agregar una plantilla de personalización de marca. Consulte [Incorporación de la marca de su organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md)
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="encrypted-emails-that-you-can-revoke"></a>Correos electrónicos cifrados que puede revocar

Los administradores y los remitentes de mensajes pueden revocar correos electrónicos cifrados si el destinatario recibió un correo electrónico cifrado basado en vínculos y con marca. Si el destinatario recibió una experiencia insertada nativa en un cliente de Outlook compatible, no puede revocar el mensaje.

Si un destinatario recibe una experiencia basada en vínculos o una experiencia insertada depende del tipo de identidad de destinatario: Office 365 y los destinatarios de la cuenta microsoft (por ejemplo, outlook.com usuarios) obtienen una experiencia en línea en los clientes de Outlook compatibles. Todos los demás tipos de destinatarios, como los destinatarios de Gmail y Yahoo, obtienen una experiencia basada en vínculos.

Los administradores y los remitentes de mensajes pueden revocar los mensajes cifrados mediante el cifrado aplicado directamente desde Outlook en la Web. Por ejemplo, los mensajes cifrados con la opción Cifrar solo.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Captura de pantalla que muestra la opción Cifrar solo en Outlook en la Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Experiencia del destinatario para correos electrónicos cifrados revocados

Una vez revocado un correo electrónico, el destinatario recibe un error cuando accede al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "El remitente ha revocado el mensaje".

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Cómo revocar un mensaje cifrado que ha enviado

Puede revocar un correo que envió a un único destinatario que usa una cuenta social, como gmail.com o yahoo.com. En otras palabras, puede revocar un correo electrónico enviado a un único destinatario que recibió la experiencia basada en vínculos.

No puede revocar un correo que envió a un destinatario que usa una cuenta profesional o educativa de Office 365 o Microsoft 365 o un usuario que usa una cuenta microsoft, por ejemplo, una cuenta de outlook.com. 

Para revocar un mensaje cifrado que envió, complete estos pasos.

1. En Outlook en la Web, en la carpeta **Enviado**, vaya al mensaje que desea revocar.

   Si el correo es revocable, verá el vínculo "Quitar acceso externo" en la parte superior del mensaje.

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Captura de pantalla que muestra el correo cifrado que desea revocar en Outlook en la Web.":::

2. Haga clic en **Quitar acceso externo** para revocar el mensaje.

   El mensaje muestra que se revoca su estado.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Captura de pantalla que muestra el mensaje cifrado revocado en Outlook en la Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>Cómo revocar un mensaje cifrado como administrador

Los administradores de Microsoft 365 siguen estos pasos generales para revocar un correo electrónico cifrado válido:

- Obtenga el identificador de mensaje del correo electrónico.
- Compruebe que puede revocar el mensaje.
- Revoque el correo.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Paso 1. Obtener el identificador de mensaje del correo electrónico

Antes de poder revocar un correo cifrado, recopile el identificador de mensaje del correo. MessageId suele tener el formato siguiente:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Hay varias maneras de encontrar el identificador de mensaje del correo electrónico que desea revocar. En esta sección se describen un par de opciones, pero puede usar cualquier método que proporcione el identificador.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-microsoft-purview-compliance-portal"></a>Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante seguimiento de mensajes en el portal de cumplimiento Microsoft Purview

1. Busque el correo electrónico por remitente o destinatario mediante [Nuevo seguimiento de mensajes en portal de cumplimiento Microsoft Purview](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).

2. Una vez que haya localizado el correo electrónico, selecciónelo para abrir el panel **Detalles del seguimiento de mensajes** . Expanda **Más información** para buscar el identificador de mensaje.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-encryption-reports-in-the-microsoft-purview-compliance-portal"></a>Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante informes de cifrado de mensajes en el portal de cumplimiento Microsoft Purview

1. En el portal de cumplimiento Microsoft Purview, vaya al **informe Cifrado de mensajes**. Para obtener información sobre este informe, vea [Ver informes de seguridad de correo electrónico en el Centro de cumplimiento de seguridad&amp;](../security/office-365-security/view-email-security-reports.md).

2. Elija la tabla **Ver detalles** e identifique el mensaje que desea revocar.

3. Haga doble clic en el mensaje para ver los detalles que incluyen el identificador de mensaje.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Paso 2. Comprobar que el correo es revocable

Para comprobar si puede revocar un mensaje, compruebe si el campo Estado de revocación está visible en el informe Cifrado, en la tabla **Detalles** de la portal de cumplimiento Microsoft Purview.

Para comprobar si puede revocar un mensaje de correo electrónico determinado mediante Windows PowerShell, complete estos pasos.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Este comando devuelve el asunto del mensaje y si el mensaje es revocable. Por ejemplo,

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>Paso 3. Revocar el correo

Una vez que sepa el identificador de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico mediante el portal de cumplimiento Microsoft Purview o Windows PowerShell.

Para revocar el mensaje mediante el portal de cumplimiento Microsoft Purview

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, conéctese a la portal de cumplimiento Microsoft Purview.

2. En el **informe Cifrado**, en la tabla **Detalles** del mensaje, elija **Revocar mensaje**.

Para revocar un correo electrónico mediante Windows PowerShell, use el cmdlet Set-OMEMessageRevocation.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Para comprobar si se ha revocado el correo electrónico, ejecute el cmdlet Get-OMEMessageStatus como se indica a continuación:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Si la revocación se realizó correctamente, el cmdlet devuelve el siguiente resultado:  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-microsoft-purview-advanced-message-encryption"></a>Más información sobre el cifrado avanzado de mensajes de Microsoft Purview

- [Cifrado avanzado de mensajes de Microsoft Purview](ome-advanced-message-encryption.md)

- [Cifrado avanzado de mensajes de Microsoft Purview: expiración del correo electrónico](ome-advanced-expiration.md)

- [Descripción de la directiva de mensaje y del servicio de cumplimiento](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
