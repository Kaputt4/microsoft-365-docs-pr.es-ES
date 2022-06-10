---
title: Administrar el Cifrado de mensajes de Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 03/04/2022
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Una vez que haya terminado de configurar Office 365 Cifrado de mensajes (OME), obtenga información sobre cómo personalizar la implementación de varias maneras.
ms.openlocfilehash: 2e39f811ec23b2f3b068ef5684fca479850a8744
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66014836"
---
# <a name="manage-office-365-message-encryption"></a>Administrar el Cifrado de mensajes de Office 365

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Una vez que haya terminado de configurar Office 365 cifrado de mensajes (OME), puede personalizar la configuración de la implementación de varias maneras. Por ejemplo, puede configurar si desea habilitar códigos de paso de un solo uso, mostrar el botón **Cifrar** en Outlook en la Web y mucho más. Las tareas de este artículo describen cómo.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Administrar si los destinatarios de cuentas de Google, Yahoo y Microsoft pueden usar estas cuentas para iniciar sesión en el portal de cifrado de mensajes de Office 365

Al configurar las nuevas funcionalidades de cifrado de mensajes Office 365, los usuarios de su organización pueden enviar mensajes a destinatarios que están fuera de la organización. Si el destinatario usa un *identificador social* , como una cuenta de Google, una cuenta de Yahoo o una cuenta de Microsoft, el destinatario puede iniciar sesión en el portal de OME con un identificador social. Si lo desea, puede optar por no permitir que los destinatarios usen identificadores sociales para iniciar sesión en el portal de OME.

### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Para administrar si los destinatarios pueden usar identificadores sociales para iniciar sesión en el portal de OME

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-OMEConfiguration con el parámetro SocialIdSignIn como se indica a continuación:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Por ejemplo, para deshabilitar los identificadores sociales:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Para habilitar los identificadores sociales:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Administrar el uso de códigos de paso únicos para el portal de cifrado de mensajes de Office 365

Si el destinatario de un mensaje cifrado por OME no usa Outlook, independientemente de la cuenta usada por el destinatario, el destinatario recibe un vínculo de vista web de tiempo limitado que le permite leer el mensaje. Este vínculo incluye un código de paso único. Como administrador, puede decidir si los destinatarios pueden usar códigos de paso de un solo uso para iniciar sesión en el portal de OME.

### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Para administrar si OME genera códigos de paso únicos

1. Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización y conéctese a Exchange Online PowerShell. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-OMEConfiguration con el parámetro OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   Por ejemplo, para deshabilitar los códigos de paso de un solo uso:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Para habilitar códigos de paso de un solo uso:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Administrar la visualización del botón Cifrar en Outlook en la Web

Como administrador, puede administrar si desea mostrar este botón a los usuarios finales.

### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Para administrar si el botón Cifrar aparece en Outlook en la Web

1. Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización y conéctese a Exchange Online PowerShell. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-IRMConfiguration con el parámetro -SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Por ejemplo, para deshabilitar el botón **Cifrar** :

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Para habilitar el botón **Cifrar** :

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Habilitación del descifrado del lado del servicio de mensajes de correo electrónico para los usuarios de iOS aplicación de correo

La aplicación de correo iOS no puede descifrar los mensajes protegidos con Office 365 cifrado de mensajes. Como administrador de Microsoft 365, puede aplicar el descifrado del lado del servicio para los mensajes entregados a la aplicación de correo iOS. Cuando decide usar el descifrado del lado del servicio, el servicio envía una copia descifrada del mensaje al dispositivo iOS. El dispositivo cliente almacena una copia descifrada del mensaje. El mensaje también conserva información sobre los derechos de uso aunque la aplicación de correo iOS no aplique derechos de uso del lado cliente al usuario. El usuario puede copiar o imprimir el mensaje incluso si originalmente no tenía los derechos para hacerlo. Sin embargo, si el usuario intenta completar una acción que requiere el Microsoft 365 servidor de correo, como reenviar el mensaje, el servidor no permitirá la acción si el usuario no tenía originalmente el derecho de uso para hacerlo. Sin embargo, los usuarios finales pueden solucionar la restricción de uso "No reenviar" reenviando el mensaje desde una cuenta diferente dentro de la aplicación de correo iOS. Independientemente de si configura el descifrado de correo en el lado del servicio, los datos adjuntos al correo cifrado y protegido por derechos no se pueden ver en la aplicación de correo iOS.

Si decide no permitir que los mensajes descifrados se envíen a iOS usuarios de la aplicación de correo, los usuarios recibirán un mensaje que indica que no tienen derechos para ver el mensaje. De forma predeterminada, el descifrado de mensajes de correo electrónico en el lado del servicio no está habilitado.

Para obtener más información y ver la experiencia del cliente, consulte [Visualización de mensajes cifrados en el iPhone o iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).

### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Para administrar si iOS aplicación de correo los usuarios pueden ver mensajes protegidos por Office 365 cifrado de mensajes

1. Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización y conéctese a Exchange Online PowerShell. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-ActiveSyncOrganizations con el parámetro AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Por ejemplo, para configurar el servicio para descifrar los mensajes antes de que se envíen a aplicaciones no habilitadas, como la aplicación de correo iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   O bien, para configurar el servicio para que no envíe mensajes descifrados a aplicaciones no habilitadas:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> Las directivas de buzón individuales (OWA/ActiveSync) invalidan esta configuración (es decir, si -IRMEnabled está establecido en False en la directiva de buzón de OWA correspondiente o en la directiva de buzón de ActiveSync, estas configuraciones no se aplicarían).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Habilitación del descifrado del lado del servicio de datos adjuntos de correo electrónico para clientes de correo del explorador web

Normalmente, cuando se usa Office 365 cifrado de mensajes, los datos adjuntos se cifran automáticamente. Como administrador, puede aplicar el descifrado del lado del servicio para los datos adjuntos de correo electrónico que los usuarios descargan desde un explorador web.

Cuando se usa el descifrado del lado del servicio, el servicio envía una copia descifrada del archivo al dispositivo. El mensaje sigue cifrado. Los datos adjuntos de correo electrónico también mantienen información sobre los derechos de uso aunque el explorador no aplique derechos de uso del lado cliente al usuario. El usuario puede copiar o imprimir los datos adjuntos del correo electrónico incluso si originalmente no tenía los derechos para hacerlo. Sin embargo, si el usuario intenta completar una acción que requiere el Microsoft 365 servidor de correo, como reenviar los datos adjuntos, el servidor no permitirá la acción si el usuario no tenía originalmente el derecho de uso para hacerlo.

Independientemente de si configura el descifrado de datos adjuntos en el lado del servicio, los usuarios no pueden ver los datos adjuntos al correo cifrado y protegido por derechos en la aplicación de correo iOS.

Si decide no permitir datos adjuntos de correo electrónico descifrados, que es el valor predeterminado, los usuarios reciben un mensaje que indica que no tienen derechos para ver los datos adjuntos.

Para obtener más información sobre cómo Microsoft 365 implementa el cifrado de los correos electrónicos y los datos adjuntos de correo electrónico con la opción Encrypt-Only, vea [Opción Solo cifrado para correos electrónicos.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Para administrar si los datos adjuntos de correo electrónico se descifran al descargarlos desde un explorador web

1. Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización y conéctese a Exchange Online PowerShell. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-IRMConfiguration con el parámetro DecryptAttachmentForEncryptOnly:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Por ejemplo, para configurar el servicio para descifrar los datos adjuntos de correo electrónico cuando un usuario los descarga desde un explorador web:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   Para configurar el servicio para que deje los datos adjuntos de correo electrónico cifrados tal y como están al descargarlo:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Asegúrese de que todos los destinatarios externos usan el portal de OME para leer el correo cifrado.

Puede usar plantillas de personalización de marca personalizadas para forzar a los destinatarios a recibir un correo contenedor que les indique que lean el correo electrónico cifrado en el Portal de OME en lugar de usar Outlook o Outlook en la Web. Es posible que quiera hacerlo si desea tener un mayor control sobre cómo usan los destinatarios el correo que reciben. Por ejemplo, si los destinatarios externos ven el correo electrónico en el portal web, puede establecer una fecha de expiración para el correo electrónico y puede revocar el correo electrónico. Estas características solo se admiten a través del portal de OME. Puede usar la opción Cifrar y la opción No reenviar al crear las reglas de flujo de correo.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Usar una plantilla personalizada para forzar a todos los destinatarios externos a usar el portal de OME y para el correo electrónico cifrado

1. Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización y conéctese a Exchange Online PowerShell. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet New-TransportRule:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    donde:

   - `mail flow rule name` es el nombre que desea usar para la nueva regla de flujo de correo.

   - `option name` es o `Encrypt` `Do Not Forward`.

   - `template name` es el nombre que le dio a la plantilla de personalización de marca, por ejemplo `OME Configuration`.

   Para cifrar todo el correo electrónico externo con la plantilla "Configuración de OME" y aplicar la opción Encrypt-Only:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   Para cifrar todo el correo electrónico externo con la plantilla "Configuración de OME" y aplicar la opción No reenviar:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Personalización de la apariencia de los mensajes de correo electrónico y el portal de OME

Para obtener información detallada sobre cómo personalizar el cifrado de mensajes de Microsoft Purview para su organización, consulte [Incorporación de la marca de la organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md). Para habilitar la capacidad de realizar un seguimiento de los mensajes cifrados y revocarlos, debe agregar su personalización de marca al portal de OME.

## <a name="disable-microsoft-purview-message-encryption"></a>Deshabilitación del cifrado de mensajes de Microsoft Purview

Esperamos que no llegue a él, pero si es necesario, deshabilitar el cifrado de mensajes de Microsoft Purview es muy sencillo. En primer lugar, deberá quitar las reglas de flujo de correo que haya creado que usen el cifrado de mensajes de Microsoft Purview. Para obtener información sobre cómo quitar reglas de flujo de correo, vea [Administrar reglas de flujo de correo](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules). A continuación, complete estos pasos en Exchange Online PowerShell.

### <a name="to-disable-microsoft-purview-message-encryption"></a>Para deshabilitar el cifrado de mensajes de Microsoft Purview

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, conéctese a Exchange Online PowerShell. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Si ha habilitado el botón **Cifrar** en Outlook en la Web, deshabilíelo ejecutando el cmdlet Set-IRMConfiguration con el parámetro SimplifiedClientAccessEnabled. De lo contrario, omita este paso.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Deshabilite el cifrado de mensajes de Microsoft Purview ejecutando el cmdlet Set-IRMConfiguration con el parámetro AzureRMSLicensingEnabled establecido en false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
