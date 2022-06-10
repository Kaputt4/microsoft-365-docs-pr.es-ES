---
title: Información heredada para el cifrado de mensajes de Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
- admindeeplinkEXCHANGE
description: Obtenga información sobre cómo realizar la transición de archivos heredados a Office 365 cifrado de mensajes (OME) para su organización.
ms.openlocfilehash: 2d994e2c521f11a70c6946e2f1a9a3a1a5766ba3
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66014914"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Información heredada para el cifrado de mensajes de Office 365

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Si aún no ha movido su organización a Cifrado de mensajes de Microsoft Purview, pero ya ha implementado OME, la información de este artículo se aplica a su organización. Microsoft recomienda que realice un plan para pasar al cifrado de mensajes de Microsoft Purview tan pronto como sea razonable para su organización. Para obtener instrucciones, consulte [Configuración del cifrado de mensajes de Microsoft Purview](set-up-new-message-encryption-capabilities.md). Si desea obtener más información sobre cómo el nuevo cifrado de mensajes primero, consulte [Cifrado de](ome.md) mensajes. El resto de este artículo hace referencia al comportamiento de OME antes de la versión de Cifrado de mensajes de Microsoft Purview.

Con el cifrado de mensajes de Office 365, la organización puede enviar y recibir mensajes cifrados entre personas de dentro y fuera de la organización. Office 365 Message Encryption funciona con Outlook.com, Yahoo, Gmail y otros servicios de correo electrónico. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios previstos puedan ver el contenido del mensaje.

Estos son algunos ejemplos:

- Un empleado bancario envía extractos de tarjeta de crédito a los clientes
- Un representante de la compañía de seguros proporciona los detalles de la póliza a los clientes
- Un agente hipotecario solicita información financiera a un cliente para una solicitud de préstamo
- Un proveedor de atención médica envía información de atención médica a los pacientes
- Un abogado envía información confidencial a un cliente u otro abogado

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Funcionamiento de Office 365 cifrado de mensajes sin las nuevas funcionalidades

Office 365 Message Encryption es un servicio en línea que se basa en Microsoft Azure Rights Management (Azure RMS). Con Azure RMS, los administradores pueden definir reglas de flujo de correo para determinar las condiciones de cifrado. Por ejemplo, una regla puede requerir el cifrado de todos los mensajes dirigidos a un destinatario específico.

Cuando alguien envía un mensaje de correo electrónico en Exchange Online que coincide con una regla de cifrado, el mensaje se envía con datos adjuntos HTML. El destinatario abre los datos adjuntos HTML y sigue las instrucciones para ver el mensaje cifrado en el portal de cifrado de mensajes Office 365. El destinatario puede elegir ver el mensaje iniciando sesión con una cuenta de Microsoft o un trabajo o centro educativo asociado a Office 365, o mediante un código de paso único. El proceso de inicio de sesión ayuda a garantizar que solo los destinatarios previstos puedan ver los mensajes cifrados. Este proceso es muy diferente para el cifrado de mensajes de Microsoft Purview.

En el siguiente diagrama se resume el paso de un mensaje de correo electrónico a través del proceso de cifrado y descrifrado.

![Diagrama que muestra la ruta de acceso de un correo electrónico cifrado.](../media/O365-Office365MessageEncryption-Concept.png)

Para obtener más información, consulte [Información del servicio para el cifrado de mensajes Office 365 heredado antes de la versión de Cifrado de mensajes de Microsoft Purview](legacy-information-for-message-encryption.md#LegacyServiceInfo).

## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-microsoft-purview-message-encryption"></a>Definición de reglas de flujo de correo para Office 365 cifrado de mensajes que no usan el cifrado de mensajes de Microsoft Purview

Para habilitar Office 365 cifrado de mensajes sin las nuevas funcionalidades, los administradores de Exchange Online y Exchange Online Protection definen Exchange reglas de flujo de correo. Estas reglas determinan en qué condiciones se deben cifrar los mensajes de correo electrónico, así como las condiciones para quitar el cifrado de mensajes. Cuando se establece una acción de cifrado para una regla, el servicio realiza la acción en cualquier mensaje que coincida con las condiciones de regla antes de enviar los mensajes.

Las reglas de flujo de correo son flexibles, lo que le permite combinar condiciones para que pueda cumplir requisitos de seguridad específicos en una sola regla. Por ejemplo, puede crear una regla para cifrar todos los mensajes que contienen palabras clave especificadas y que se dirigen a destinatarios externos. Office 365 El cifrado de mensajes también cifra las respuestas de los destinatarios del correo electrónico cifrado y puede crear una regla que descifre esas respuestas como una comodidad para los usuarios de correo electrónico. De este modo, los usuarios de su organización no tendrán que iniciar sesión en el portal de cifrado para ver las respuestas.

Para obtener más información sobre cómo crear reglas de flujo de correo Exchange, vea [Definir reglas para Office 365 cifrado de mensajes](define-mail-flow-rules-to-encrypt-email.md).

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-microsoft-purview-message-encryption"></a>Uso del EAC para crear una regla de flujo de correo para cifrar mensajes de correo electrónico sin cifrado de mensajes de Microsoft Purview

1. En un explorador web, con una cuenta profesional o educativa a la que se hayan concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administrador** .

3. En el Centro de administración de Microsoft 365, elija **Centros** \> de administración <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">**Exchange**</a>.

4. En el EAC, vaya a **Reglas** de **flujo** \> de correo y seleccione **Nuevo** ![icono nuevo.](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**Cree una nueva regla**. Para obtener más información sobre el uso del EAC, consulte [Exchange centro de administración en Exchange Online](/exchange/exchange-admin-center).

5. En **Nombre**, escriba un nombre para la regla, como Cifrar correo para DrToniRamos@hotmail.com.

6. En **Aplicar esta regla si** selecciona una condición, escriba un valor si es necesario. Por ejemplo, para cifrar los mensajes que van a DrToniRamos@hotmail.com:

   1. En **Aplicar esta regla si**, seleccione **el destinatario.**

   2. Seleccione un nombre existente en la lista de contactos o escriba una nueva dirección de correo electrónico en la casilla **nombres** .

      - Para seleccionar un nombre existente, selecciónelo en la lista y haga clic en **Aceptar**.

      - Para escribir un nombre nuevo, escriba una dirección de correo electrónico en la casilla **de verificación nombres** y, a continuación, active **los nombres** \> **correctos**.

7. Para agregar más condiciones, elija **Más opciones** y, a continuación, seleccione **Agregar condición** y seleccione en la lista.

   Por ejemplo, para aplicar la regla solo si el destinatario está fuera de su organización, seleccione **Agregar condición** y, a continuación, seleccione **El destinatario es externo o interno** \> **Fuera de la organización** \> **Aceptar**.

8. Para habilitar el cifrado sin usar las nuevas funcionalidades de OME, en **Haga lo siguiente**, seleccione **Modificar la seguridad** \> del mensaje **Aplicar la versión anterior de OME** y, a continuación, elija **Guardar**.

   Si recibe un error que indica que las licencias de IRM no están habilitadas, no usará OME heredado.

9. (Opcional) Elija **Agregar acción** para especificar otra acción.

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Usar Exchange Online PowerShell para crear una regla de flujo de correo para cifrar mensajes de correo electrónico sin las nuevas funcionalidades de OME

1. Conéctese a Exchange Online PowerShell. Para obtener más información, vea [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Cree una regla mediante el cmdlet **New-TransportRule** y establezca el parámetro _ApplyOME_ en `$true`.

   Este ejemplo requiere que todos los mensajes de correo electrónico enviados a DrToniRamos@hotmail.com se cifren.

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   Donde,

   - El nombre único de la nueva regla es "Encrypt rule for Dr Toni Ramos".
   - El parámetro _SentTo_ especifica los destinatarios del mensaje (identificados por nombre, dirección de correo electrónico, nombre distintivo, etc.). En este ejemplo, el destinatario se identifica mediante la dirección de correo electrónico "DrToniRamos@hotmail.com".
   - El parámetro _SentToScope_ especifica la ubicación de los destinatarios del mensaje. En este ejemplo, el buzón del destinatario está en hotmail y no forma parte de la organización, por lo que se usa el valor `NotInOrganization` .

   Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](/powershell/module/exchange/New-TransportRule).

### <a name="remove-encryption-from-email-replies-encrypted-without-microsoft-purview-message-encryption"></a>Eliminación del cifrado de respuestas de correo electrónico cifradas sin cifrado de mensajes de Microsoft Purview

Cuando los usuarios de correo electrónico envían mensajes cifrados, los destinatarios de esos mensajes pueden responder con respuestas cifradas. Puede crear reglas de flujo de correo para quitar automáticamente el cifrado de las respuestas para que los usuarios de correo electrónico de su organización no tengan que iniciar sesión en el portal de cifrado para verlos. Puede usar el EAC o Exchange Online cmdlets de PowerShell para definir estas reglas. Puede descifrar los mensajes que se envían desde dentro de la organización o mensajes que son respuestas a los mensajes enviados desde dentro de la organización. No se pueden descifrar los mensajes cifrados que se originen fuera de la organización.

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-microsoft-purview-message-encryption"></a>Uso del EAC para crear una regla para quitar el cifrado de las respuestas de correo electrónico cifradas sin el cifrado de mensajes de Microsoft Purview

1. En un explorador web, con una cuenta profesional o educativa a la que se le hayan concedido permisos de administrador, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administrador** .

3. En el Centro de administración de Microsoft 365, elija **Centros** \> de administración <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">**Exchange**</a>.

4. En el EAC, vaya a **Reglas** de **flujo** \> de correo y seleccione **Nuevo** ![icono nuevo.](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**Cree una nueva regla**. Para obtener más información sobre el uso del EAC, consulte [Exchange centro de administración en Exchange Online](/exchange/exchange-admin-center).

5. En **Nombre**, escriba un nombre para la regla, como Quitar cifrado del correo entrante.

6. En **Aplicar esta regla si** selecciona las condiciones en las que se debe quitar el cifrado de los mensajes, como **El destinatario se encuentra** \> **dentro de la organización**.

7. En **Haga lo siguiente**, seleccione **Modificar la seguridad** \> del mensaje **Quitar la versión anterior de OME**.

8. Seleccione **Guardar**.

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Use Exchange Online PowerShell para crear una regla para quitar el cifrado de las respuestas de correo electrónico cifradas sin las nuevas funcionalidades de OME

1. Conéctese a Exchange Online PowerShell. Para obtener más información, vea [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Cree una regla mediante el cmdlet **New-TransportRule** y establezca el parámetro _RemoveOME_ en `$true`.

   En este ejemplo se quita el cifrado de todo el correo enviado a los destinatarios de la organización.

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   Donde,

   - El nombre único de la nueva regla es "Quitar el cifrado del correo entrante".
   - El parámetro _SentToScope_ especifica la ubicación de los destinatarios del mensaje. En este ejemplo, se usa el valor de valor `InOrganization` , que indica uno de los siguientes elementos:
     - El destinatario es un buzón, un usuario de correo, un grupo o una carpeta pública habilitada para correo en su organización.
     - La dirección de correo electrónico del destinatario está en un dominio aceptado configurado como dominio autoritativo o como un dominio de retransmisión interno de su organización _, y_ el mensaje se envió o recibió a través de una conexión autenticada.

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](/powershell/module/exchange/New-TransportRule).

## <a name="sending-viewing-and-replying-to-messages-encrypted-without-the-new-capabilities"></a>Envío, visualización y respuesta a mensajes cifrados sin las nuevas funcionalidades

Con Office 365 cifrado de mensajes, los mensajes de correo electrónico se cifran automáticamente, en función de las reglas definidas por el administrador. Un correo electrónico que lleva un mensaje cifrado llega a la Bandeja de entrada del destinatario con un archivo HTML adjunto.

Los destinatarios siguen las instrucciones del mensaje para abrir los datos adjuntos y autenticarse mediante una cuenta de Microsoft o una empresa o escuela asociada a Office 365. Si los destinatarios no tienen ninguna de las dos cuentas, se les dirige a crear una cuenta microsoft que les permita iniciar sesión para ver el mensaje cifrado. Como alternativa, los destinatarios pueden elegir obtener un código de paso único para ver el mensaje. Después de iniciar sesión o usar un código de paso único, los destinatarios pueden ver el mensaje descifrado y enviar una respuesta cifrada.

## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Personalización de mensajes cifrados con Office 365 cifrado de mensajes

Como administrador Exchange Online y Exchange Online Protection, puede personalizar los mensajes cifrados. Por ejemplo, puede agregar la marca y el logotipo de su empresa, especificar una introducción y agregar texto de declinación de responsabilidades en mensajes cifrados y en el portal donde los destinatarios ven los mensajes cifrados. Con Exchange Online cmdlets de PowerShell, puede personalizar los siguientes aspectos de la experiencia de visualización para los destinatarios de mensajes de correo electrónico cifrados:

- Texto introductorio del correo electrónico que contiene el mensaje cifrado
- Texto de declinación de responsabilidades del correo electrónico que contiene el mensaje cifrado
- Texto del portal que aparecerá en el portal de visualización de mensajes
- Logotipo que aparecerá en el mensaje de correo electrónico y en el portal de visualización

También puede volver a la apariencia predeterminada en cualquier momento.

En el ejemplo siguiente se muestra un logotipo personalizado para ContosoPharma en los datos adjuntos del correo electrónico:

> [!div class="mx-imgBorder"]
> ![Ejemplo de la página de mensajes cifrados de la vista.](../media/TA-OME-3attachment2.jpg)

### <a name="to-customize-encryption-email-messages-and-the-encryption-portal-with-your-organizations-brand"></a>Para personalizar los mensajes de correo electrónico de cifrado y el portal de cifrado con la marca de su organización

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use el cmdlet Set-OMEConfiguration como se describe aquí: [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) o use la tabla siguiente para obtener instrucciones.

   **Opciones de personalización de cifrado**

   |Para personalizar esta característica de la experiencia de cifrado|Use estos comandos de PowerShell Exchange Online|
   |---|---|
   |Texto predeterminado que acompaña a mensajes de correo electrónico cifrados <p> El texto predeterminado aparece encima de las instrucciones para ver los mensajes cifrados|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <p> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"`|
   |Declaración de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <p> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"`|
   |Texto que aparece en la parte superior del portal de visualización de correo cifrado|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <p> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"`|
   |Logotipo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <p> **Ejemplo:** `Set-OMEConfiguration -Identity "OME configuration" -Image ([System.IO.File]::ReadAllBytes('C:\Temp\contosologo.png'))` <p> Formatos de archivo compatibles: .png, .jpg, .bmp o .tiff <p> Tamaño óptimo del archivo de logotipo: menos de 40 KB <p> Tamaño óptimo de la imagen del logotipo: 170 x 70 píxeles|

### <a name="to-remove-brand-customizations-from-encryption-email-messages-and-the-encryption-portal"></a>Para quitar las personalizaciones de marca de los mensajes de correo electrónico de cifrado y el portal de cifrado

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use el cmdlet Set-OMEConfiguration como se describe aquí: [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration). Para quitar las personalizaciones de marca de la organización de los valores DisclaimerText, EmailText y PortalText, establezca el valor en una cadena vacía, `""`. Para todos los valores de imagen, como Logo, establezca el valor `"$null"`en .

   **Opciones de personalización de cifrado**

   |Para revertir esta característica de la experiencia de cifrado al texto e imagen predeterminados|Use estos comandos de PowerShell Exchange Online|
   |---|---|
   |Texto predeterminado que acompaña a mensajes de correo electrónico cifrados <p> El texto predeterminado aparece encima de las instrucciones para ver los mensajes cifrados|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <p> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Declaración de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado <p> |`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <p> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Texto que aparece en la parte superior del portal de visualización de correo cifrado|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <p> **Ejemplo de reversión al valor predeterminado:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logotipo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <p> **Ejemplo de reversión al valor predeterminado:** `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>Información del servicio para el cifrado de mensajes Office 365 heredado antes de la publicación de las nuevas funcionalidades de OME
<a name="LegacyServiceInfo"> </a>

En la tabla siguiente se proporcionan detalles técnicos del servicio de cifrado de mensajes de Office 365 antes de la versión de Cifrado de mensajes de Microsoft Purview.

|Detalles del servicio|Descripción|
|---|---|
|Requisitos de dispositivo de cliente|Los mensajes cifrados se pueden ver en cualquier dispositivo de cliente, siempre y cuando los datos adjuntos HTML puedan abrirse en un explorador moderno que admita el envío de formularios.|
|Algoritmo de cifrado y compatibilidad con FIPS (Estándar federal de procesamiento de información)|El Cifrado de mensajes de Office 365 emplea las mismas claves de cifrado que Microsoft Azure Information Rights Management (IRM) y admite el modo criptográfico 2 (clave de 2048 bits para RSA y de 256 bits para sistemas SHA-1). Para obtener más información sobre los modos criptográficos IRM subyacentes, consulte [Modos criptográficos de AD RMS](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)).|
|Tipos de mensaje admitidos|Solo se admite el cifrado de mensajes de Office 365 para los elementos que tienen un identificador de clase de mensaje de **IPM.Note**. Para obtener más información, vea [Tipos de elementos y clases de mensaje](/office/vba/outlook/Concepts/Forms/item-types-and-message-classes).|
|Límites de tamaño de mensaje|El Cifrado de mensajes de Office 365 es capaz de cifrar mensajes de hasta 25 megabytes. Para obtener más información sobre los límites de tamaño del mensaje, consulte [Límites de Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).|
|Exchange Online directivas de retención de correo electrónico|Exchange Online no almacena los mensajes cifrados.|
|Compatibilidad de idiomas en el cifrado de mensajes de Office 365|Office 365 cifrado de mensajes admite lenguajes de Microsoft 365, como se indica a continuación: <p> Los mensajes de correo electrónico entrantes y los archivos HTML adjuntos se localizan en función de la configuración de idioma del remitente. <p> El portal de visualización se localiza en función de la configuración del explorador del destinatario. <p> El cuerpo (contenido) del mensaje cifrado no se localiza.|
|Información de privacidad del Portal OME y la aplicación Visor OME|El vínculo [Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/privacystatement) proporciona más información sobre el uso de su información privada por parte de Microsoft.|

## <a name="frequently-asked-questions-about-legacy-ome"></a>Preguntas más frecuentes sobre OME heredado
<a name="LegacyServiceInfo"> </a>

¿Tiene preguntas sobre Office 365 cifrado de mensajes? Aquí encontrará algunas respuestas. Si no encuentra lo que necesita, consulte los [foros de Microsoft Tech Community para obtener Office 365](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365).

 **Q. Mis usuarios envían mensajes de correo electrónico cifrados a destinatarios fuera de nuestra organización. ¿Hay algo que los destinatarios externos tengan que hacer para leer y responder a los mensajes de correo electrónico cifrados con Office 365 cifrado de mensajes?**

Los destinatarios de fuera de la organización que reciben Microsoft 365 mensajes cifrados pueden verlos de una de estas dos maneras:

- Iniciando sesión con una cuenta microsoft o una cuenta profesional o educativa asociada a Office 365.

- Mediante el uso de un código de paso único.

 **Q. ¿Se almacenan Microsoft 365 mensajes cifrados en la nube o en servidores de Microsoft?**

No, los mensajes cifrados se mantienen en el sistema de correo electrónico del destinatario y, cuando el destinatario abre el mensaje, se publica temporalmente para su visualización en servidores de Microsoft. Pero los mensajes no se almacenan ahí.

 **P. ¿Puedo personalizar los mensajes de correo electrónico cifrado con mi marca?**

Sí. Puede usar Exchange Online cmdlets de PowerShell para personalizar el texto predeterminado que aparece en la parte superior de los mensajes de correo electrónico cifrados, el texto de la declinación de responsabilidades y el logotipo que desea usar para el mensaje de correo electrónico y el portal de cifrado. Esta característica ya está disponible en OMEv2. Para más información, consulte [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).

 **P. ¿Requiere el servicio una licencia para cada usuario de la organización?**

Se requiere una licencia para cada usuario de la organización que envíe correo electrónico cifrado.

 **P. ¿Requieren los destinatarios externos suscripciones?**

No, los destinatarios externos no requieren una suscripción para leer o responder los mensajes cifrados.

 **Q. ¿En qué se diferencia Office 365 cifrado de mensajes de Rights Management Services (RMS)?**

RMS proporciona funcionalidades de Information Rights Protection para los correos electrónicos internos de una organización proporcionando plantillas integradas, como: No reenviar y Company Confidential. El cifrado de mensajes de Office 365 es compatible con el cifrado para los mensajes de correo electrónico que se envían a destinatarios externos, así como destinatarios internos.

 **Q. ¿En qué se diferencia Office 365 cifrado de mensajes de S/MIME?**

S/MIME es básicamente una tecnología de cifrado del lado cliente y requiere la administración de certificados complicados y la publicación de infraestructura. Office 365 cifrado de mensajes usa reglas de flujo de correo (también conocidas como reglas de transporte) y no depende de la publicación de certificados.

 **P. ¿Puedo leer los mensajes cifrados en dispositivos móviles?**

Sí, puede ver mensajes en Android y iOS descargando las aplicaciones del Visor de OME desde Google Play Store y Apple App Store. Abra los datos adjuntos en formato HTML en la aplicación del Visor de OME y, a continuación, siga las instrucciones para abrir el mensaje cifrado. Para otros dispositivos móviles, puede abrir los datos adjuntos en formato HTML siempre que el cliente de correo permita la publicación de formularios.

 **P. ¿Se cifran las respuestas y los mensajes reenviados?**

Sí. Las respuestas se siguen cifrando durante todo el período de la conversación.

 **Q. ¿Office 365 cifrado de mensajes proporciona localización?**

El correo electrónico entrante y el contenido HTML se localiza según la configuración de correo electrónico del remitente. El portal de visualización se localiza según la configuración del explorador del destinatario. Sin embargo, el cuerpo (contenido) del mensaje cifrado no se localiza.

 **Q. ¿Qué método de cifrado se usa para Office 365 cifrado de mensajes?**

Office 365 Message Encryption usa Rights Management Services (RMS) como infraestructura de cifrado. El método de cifrado utilizado depende de dónde obtiene las claves de RMS utilizadas para cifrar y descifrar mensajes.

- Si usa Microsoft Azure RMS para obtener las claves, se usa el modo criptográfico 2. El modo criptográfico 2 es una implementación criptográfica de AD RMS actualizada y mejorada. Es compatible con RSA 2048 para firma y cifrado, y admite SHA-256 para firma.

- Si usa Active Directory (AD) RMS para obtener las claves, se utiliza el modo criptográfico 1 o el modo criptográfico 2. El método empleado depende de la implementación local de AD RMS. El modo criptográfico 1 es la implementación criptográfica original de AD RMS. Es compatible con RSA 1024 para firma y cifrado, y admite SHA-1 para firma. Este modo sigue siendo compatible con todas las versiones actuales de RMS.

Para obtener más información, vea [Modos criptográficos de AD RMS](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)).

**Q. ¿Por qué algunos mensajes cifrados dicen que proceden de** Office365@messaging.microsoft.com?

Cuando se envía una respuesta cifrada desde el portal de cifrado o a través de la aplicación del Visor de OME, la dirección de correo electrónico de envío se establece en Office365@messaging.microsoft.com porque el mensaje cifrado se envía a través de un extremo de Microsoft. Esto ayuda a evitar que los mensajes cifrados se marquen como correo no deseado. El nombre mostrado en el correo electrónico y la dirección del portal de cifrado no se modifican a causa de este etiquetado. Además, este etiquetado solo se aplica a los mensajes enviados a través del portal, no a través de cualquier otro cliente de correo electrónico.

 **Q. Soy un suscriptor de cifrado hospedado Exchange (EHE). ¿Dónde puedo obtener más información sobre la actualización a Office 365 cifrado de mensajes?**

Todos los clientes de EHE se han actualizado a Cifrado de mensajes de Office 365. Para obtener más información, visite el [Centro de actualización de cifrado hospedado de Exchange](../security/office-365-security/exchange-online-protection-overview.md).

 **Q. ¿Es necesario abrir direcciones URL, direcciones IP o puertos en el firewall de mi organización para admitir Office 365 cifrado de mensajes?**

Sí. Debe agregar direcciones URL para Exchange Online para que la lista de permitidos de la organización habilite la autenticación de los mensajes cifrados por parte del servicio de cifrado de mensajes de Office 365. Para obtener una lista de direcciones URL de Exchange Online, consulte [Microsoft 365 direcciones URL e intervalos de direcciones IP](../enterprise/urls-and-ip-address-ranges.md).

 **Q. ¿A cuántos destinatarios puedo enviar un mensaje cifrado de Microsoft 365?**

El límite de destinatarios es de 500 destinatarios por mensaje o, cuando se combina después de la expansión de la lista de distribución, 11 980 caracteres en el campo **Para** del mensaje, lo que ocurra primero.

 **P. ¿Es posible revocar un mensaje enviado a un destinatario concreto?**

No. No puede revocar un mensaje a una persona determinada después de enviarlo.

 **P. ¿Puedo ver un informe de los mensajes cifrados que se han recibido y leído?**

No hay un informe que muestre si se ha visto un mensaje cifrado, pero hay Microsoft 365 informes disponibles que puede aprovechar para determinar el número de mensajes que coincidieron con una regla de flujo de correo específica (también conocida como regla de transporte), por ejemplo.

 **P. ¿Qué hace Microsoft con la información que proporciono a través del Portal OME y la aplicación Visor OME?**

La [declaración de privacidad del portal de cifrado de mensajería de Office 365](https://privacy.microsoft.com/privacystatement) proporciona información detallada sobre lo que Hace Microsoft y no hace con su información privada.

**Q. ¿Qué hago si no recibo el código de paso único después de solicitarlo?**

En primer lugar, compruebe la carpeta de correo no deseado en el cliente de correo electrónico. La configuración de DKIM y DMARC para su organización puede hacer que estos correos electrónicos terminen filtrados como correo no deseado.

A continuación, compruebe la cuarentena en el Centro de cumplimiento de seguridad &. A menudo, los mensajes que contienen un código de paso único, especialmente los primeros que recibe su organización, terminan en cuarentena.
