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
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Una vez que haya terminado de configurar el cifrado de mensajes (OME) de Office 365, obtenga información sobre cómo personalizar la implementación de varias maneras.
ms.openlocfilehash: 06e9d22d51c05fe9f7bc4c1a014607feafbf2dba
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908190"
---
# <a name="manage-office-365-message-encryption"></a>Administrar el Cifrado de mensajes de Office 365

Una vez que haya terminado de configurar el cifrado de mensajes (OME) de Office 365, puede personalizar la configuración de la implementación de varias maneras. Por ejemplo, puede configurar si desea habilitar códigos de paso único, mostrar el botón **Cifrar** en Outlook en la web y mucho más. Las tareas de este artículo describen cómo hacerlo.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Administrar si los destinatarios de cuentas de Google, Yahoo y Microsoft pueden usar estas cuentas para iniciar sesión en el portal de cifrado de mensajes de Office 365

Al configurar las nuevas funcionalidades de cifrado de mensajes de Office 365, los usuarios de la organización pueden enviar mensajes a destinatarios que están fuera de la organización. Si el destinatario usa un *identificador social* como una cuenta de Google, una cuenta de Yahoo o una cuenta microsoft, el destinatario puede iniciar sesión en el portal de OME con un identificador social. Si lo desea, puede elegir no permitir que los destinatarios usen los IDs sociales para iniciar sesión en el portal de OME.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Para administrar si los destinatarios pueden usar los IDs sociales para iniciar sesión en el portal de OME
  
1. [Conectarse a Exchange Online mediante PowerShell remoto.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Ejecute el cmdlet Set-OMEConfiguration con el parámetro SocialIdSignIn de la siguiente manera:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Por ejemplo, para deshabilitar los IDs sociales:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Para habilitar los IDs sociales:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Administrar el uso de códigos de paso único para el portal de cifrado de mensajes de Office 365

Si el destinatario de un mensaje cifrado por OME no usa Outlook, independientemente de la cuenta usada por el destinatario, el destinatario recibe un vínculo de vista web de tiempo limitado que le permite leer el mensaje. Este vínculo incluye un código de paso único. Como administrador, puede decidir si los destinatarios pueden usar códigos de paso único para iniciar sesión en el portal de OME.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Para administrar si OME genera códigos de paso único
  
1. Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización e inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-OMEConfiguration con el parámetro OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Por ejemplo, para deshabilitar códigos de paso único:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Para habilitar códigos de paso único:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Administrar la presentación del botón Cifrar en Outlook en la web

Como administrador, puede administrar si desea mostrar este botón a los usuarios finales.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Para administrar si el botón Cifrar aparece en Outlook en la web
  
1. Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización e inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-IRMConfiguration con el parámetro -SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Por ejemplo, para deshabilitar el **botón Cifrar:**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Para habilitar el **botón Cifrar:**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Habilitar el descifrado del lado del servicio de mensajes de correo electrónico para usuarios de la aplicación de correo de iOS

La aplicación de correo de iOS no puede descifrar mensajes protegidos con cifrado de mensajes de Office 365. Como administrador de Microsoft 365, puedes aplicar descifrado del lado del servicio para los mensajes entregados a la aplicación de correo de iOS. Cuando eliges usar el descifrado del lado del servicio, el servicio envía una copia descifrada del mensaje al dispositivo iOS. El dispositivo cliente almacena una copia descifrada del mensaje. El mensaje también conserva información sobre los derechos de uso aunque la aplicación de correo de iOS no aplica derechos de uso del lado cliente al usuario. El usuario puede copiar o imprimir el mensaje incluso si originalmente no tenía los derechos para hacerlo. Sin embargo, si el usuario intenta completar una acción que requiere el servidor de correo de Microsoft 365, como reenviar el mensaje, el servidor no permitirá la acción si el usuario no tenía originalmente el derecho de uso para hacerlo. Sin embargo, los usuarios finales pueden evitar la restricción de uso "No reenviar" reenviando el mensaje desde una cuenta diferente dentro de la aplicación de correo de iOS. Independientemente de si configura el descifrado del lado del servicio del correo, los datos adjuntos al correo cifrado y protegido con derechos no se pueden ver en la aplicación de correo de iOS.
  
Si decides no permitir que los mensajes descifrados se envíen a los usuarios de la aplicación de correo de iOS, los usuarios recibirán un mensaje que indica que no tienen los derechos para ver el mensaje. De forma predeterminada, el descifrado del lado del servicio de los mensajes de correo electrónico no está habilitado.
  
Para obtener más información y ver la experiencia del cliente, consulta [Ver mensajes cifrados en tu iPhone o iPad.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Para administrar si los usuarios de la aplicación de correo de iOS pueden ver mensajes protegidos por el cifrado de mensajes de Office 365
  
1. Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización e inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-ActiveSyncOrganizations con el parámetro AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Por ejemplo, para configurar el servicio para descifrar mensajes antes de que se envíen a aplicaciones no disponibles, como la aplicación de correo de iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   O bien, para configurar el servicio para que no envíe mensajes descifrados a aplicaciones sin iluminación:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> Las directivas de buzones individuales (OWA/ActiveSync) invalidan esta configuración (es decir, si -IRMEnabled se establece en False dentro de la directiva de buzones de OWA respectiva o en la directiva de buzones de Correo de ActiveSync, estas configuraciones no se aplicarían).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Habilitar el descifrado del lado del servicio de datos adjuntos de correo electrónico para clientes de correo del explorador web

Normalmente, al usar el cifrado de mensajes de Office 365, los datos adjuntos se cifran automáticamente. Como administrador, puede aplicar el descifrado del lado del servicio para los datos adjuntos de correo electrónico que los usuarios descargan desde un explorador web.
  
Al usar el descifrado del lado del servicio, el servicio envía una copia descifrada del archivo al dispositivo. El mensaje todavía está cifrado. Los datos adjuntos de correo electrónico también mantienen información sobre los derechos de uso aunque el explorador no aplique derechos de uso del lado cliente al usuario. El usuario puede copiar o imprimir los datos adjuntos del correo electrónico incluso si originalmente no tenían los derechos para hacerlo. Sin embargo, si el usuario intenta completar una acción que requiere el servidor de correo de Microsoft 365, como reenviar los datos adjuntos, el servidor no permitirá la acción si el usuario no tenía originalmente el derecho de uso para hacerlo.
  
Independientemente de si configura el descifrado del lado del servicio de datos adjuntos, los usuarios no pueden ver datos adjuntos al correo cifrado y protegido con derechos en la aplicación de correo de iOS.
  
Si decide no permitir datos adjuntos de correo electrónico descifrados, que es el valor predeterminado, los usuarios recibirán un mensaje que indica que no tienen derechos para ver los datos adjuntos.
  
Para obtener más información acerca de cómo Microsoft 365 implementa el cifrado para correos electrónicos y datos adjuntos de correo electrónico con la opción Encrypt-Only, consulte [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Para administrar si los datos adjuntos de correo electrónico se descifran al descargarlos desde un explorador web
  
1. Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización e inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-IRMConfiguration con el parámetro DecryptAttachmentForEncryptOnly:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Por ejemplo, para configurar el servicio para descifrar datos adjuntos de correo electrónico cuando un usuario los descarga desde un explorador web:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   Para configurar el servicio para que deje los datos adjuntos de correo electrónico cifrados tal como están al descargarlos:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Asegúrese de que todos los destinatarios externos usan el Portal de OME para leer correo cifrado

Puede usar plantillas de personalización de marca personalizadas para forzar a los destinatarios a recibir un correo contenedor que los dirija a leer correo electrónico cifrado en el Portal de OME en lugar de usar Outlook o Outlook en la web. Es posible que desee hacer esto si desea un mayor control sobre cómo los destinatarios usan el correo que reciben. Por ejemplo, si los destinatarios externos ven el correo electrónico en el portal web, puede establecer una fecha de expiración para el correo electrónico y puede revocar el correo electrónico. Estas características solo se admiten a través del Portal de OME. Puede usar las opciones Cifrar y No reenviar al crear las reglas de flujo de correo.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Usar una plantilla personalizada para forzar a todos los destinatarios externos a usar el Portal de OME y para el correo electrónico cifrado

1. Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización e inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet New-TransportRule:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    donde:

   - `mail flow rule name` es el nombre que desea usar para la nueva regla de flujo de correo.

   - `option name` es o `Encrypt` `Do Not Forward` .

   - `template name` es el nombre que ha dado a la plantilla de personalización de marca personalizada, por ejemplo `OME Configuration` .

   Para cifrar todo el correo electrónico externo con la plantilla "Configuración de OME" y aplicar la Encrypt-Only:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   Para cifrar todo el correo electrónico externo con la plantilla "Configuración de OME" y aplicar la opción No reenviar:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Personalizar la apariencia de los mensajes de correo electrónico y el portal de OME

Para obtener información detallada sobre cómo personalizar OME para su organización, vea Agregar la marca de la organización [a los mensajes cifrados.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="disable-the-new-capabilities-for-ome"></a>Deshabilitar las nuevas funcionalidades para OME

Esperamos que no lo haga, pero si es necesario, deshabilitar las nuevas capacidades para OME es muy sencillo. En primer lugar, deberá quitar las reglas de flujo de correo que haya creado que usen las nuevas funcionalidades de OME. Para obtener información sobre cómo quitar reglas de flujo de correo, vea [Administrar reglas de flujo de correo](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules). A continuación, siga estos pasos en Exchange Online PowerShell.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Para deshabilitar las nuevas funcionalidades de OME
  
1. Con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Si ha habilitado el **botón Cifrar** en Outlook en la web, deshabilite el cmdlet Set-IRMConfiguration con el parámetro SimplifiedClientAccessEnabled. De lo contrario, omita este paso.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Para deshabilitar las nuevas funcionalidades de OME, ejecute el cmdlet Set-IRMConfiguration con el parámetro AzureRMSLicensingEnabled establecido en false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```