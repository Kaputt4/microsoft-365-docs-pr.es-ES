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
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Comprenda cómo realizar la transición de archivos heredados a Cifrado de mensajes de Office 365 (OME) para su organización.
ms.openlocfilehash: eabf655b6fa92a6f502ebe1e071d41f394f78929
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051832"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Información heredada para el cifrado de mensajes de Office 365

Si aún no ha movido la organización a las nuevas funcionalidades de OME, pero ya ha implementado OME, la información de este artículo se aplica a su organización. Microsoft recomienda realizar un plan para pasar a las nuevas funcionalidades de OME tan pronto como sea razonable para su organización. Para obtener instrucciones, consulte [Set up new Cifrado de mensajes de Office 365 capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). Si desea obtener más información sobre cómo funcionan primero las nuevas funcionalidades, [vea Cifrado de mensajes de Office 365](ome.md). El resto de este artículo hace referencia al comportamiento de OME antes del lanzamiento de las nuevas funcionalidades de OME.
  
Con el cifrado de mensajes de Office 365, la organización puede enviar y recibir mensajes cifrados entre personas de dentro y fuera de la organización. Cifrado de mensajes de Office 365 funciona con Outlook.com, Yahoo, Gmail y otros servicios de correo electrónico. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios previstos puedan ver el contenido del mensaje.
  
Estos son algunos ejemplos:
  
- Un empleado del banco envía extractos de tarjeta de crédito a los clientes

- Un representante de la compañía de seguros proporciona detalles de la directiva a los clientes

- Un agente de hipotecas solicita información financiera a un cliente para una solicitud de préstamo

- Un proveedor de atención médica envía información de atención médica a los pacientes

- Un abogado envía información confidencial a un cliente u otro abogado

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Cómo Cifrado de mensajes de Office 365 sin las nuevas funcionalidades

Cifrado de mensajes de Office 365 es un servicio en línea que se basa en Microsoft Azure Rights Management (Azure RMS). Con Azure RMS, los administradores pueden definir reglas de flujo de correo para determinar las condiciones del cifrado. Por ejemplo, una regla puede requerir el cifrado de todos los mensajes dirigidos a un destinatario específico.
  
Cuando alguien envía un mensaje de correo electrónico Exchange Online que coincide con una regla de cifrado, el mensaje se envía con datos adjuntos HTML. El destinatario abre los datos adjuntos HTML y sigue las instrucciones para ver el mensaje cifrado en Cifrado de mensajes de Office 365 portal. El destinatario puede elegir ver el mensaje iniciando sesión con una cuenta de Microsoft o un trabajo o escuela asociados con Office 365, o mediante un código de pase único. El proceso de inicio de sesión ayuda a garantizar que solo los destinatarios previstos puedan ver los mensajes cifrados. Este proceso es muy diferente para las nuevas funcionalidades de OME.
  
En el siguiente diagrama se resume el paso de un mensaje de correo electrónico a través del proceso de cifrado y descrifrado.
  
![Diagrama que muestra la ruta de acceso de un correo electrónico cifrado](../media/O365-Office365MessageEncryption-Concept.png)
  
Para obtener más información, vea [Service information for legacy Cifrado de mensajes de Office 365 prior to the release of the new OME capabilities](legacy-information-for-message-encryption.md#LegacyServiceInfo).
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>Definición de reglas de flujo de correo Cifrado de mensajes de Office 365 que no usan las nuevas funcionalidades de OME

Para habilitar Cifrado de mensajes de Office 365 sin las nuevas funcionalidades, Exchange Online y Exchange Online Protection administradores definen Exchange de flujo de correo. Estas reglas determinan en qué condiciones deben cifrarse los mensajes de correo electrónico, así como las condiciones para quitar el cifrado de mensajes. Cuando se establece una acción de cifrado para una regla, el servicio realiza la acción en los mensajes que coinciden con las condiciones de la regla antes de enviar los mensajes.

Las reglas de flujo de correo son flexibles, lo que le permite combinar condiciones para que pueda cumplir requisitos de seguridad específicos en una sola regla. Por ejemplo, puede crear una regla para cifrar todos los mensajes que contienen palabras clave especificadas y están dirigidos a destinatarios externos. Cifrado de mensajes de Office 365 también cifra las respuestas de los destinatarios del correo electrónico cifrado y puede crear una regla que descifra esas respuestas como una comodidad para los usuarios de correo electrónico. De este modo, los usuarios de la organización no tendrán que iniciar sesión en el portal de cifrado para ver las respuestas.
  
Para obtener más información acerca de cómo crear Exchange de flujo de correo, vea [Definir reglas para Cifrado de mensajes de Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Usar el EAC para crear una regla de flujo de correo para cifrar mensajes de correo electrónico sin las nuevas funcionalidades de OME

1. En un explorador web, con una cuenta de trabajo o escuela a la que se han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el **icono** Administrador.

3. En el centro Microsoft 365 administración, elija **Centros de administración** \> **Exchange**.

4. En el EAC, vaya a **Flujo de correo** \> **Reglas** y **seleccione Nuevo** icono Nuevo ![ Crear una nueva ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regla**. Para obtener más información acerca del uso del EAC, vea [Exchange centro de administración en Exchange Online](/exchange/exchange-admin-center).

5. En **Nombre**, escriba un nombre para la regla, como Cifrar correo para DrToniRamos@hotmail.com.

6. En **Aplicar esta regla si** selecciona una condición y escribe un valor si es necesario. Por ejemplo, para cifrar mensajes que van a DrToniRamos@hotmail.com:

   1. En **Aplicar esta regla si**, seleccione el destinatario **es**.

   2. Seleccione un nombre existente de la lista de contactos o escriba una nueva dirección de correo electrónico en la **casilla nombres.**

      - Para seleccionar un nombre existente, selecciónelo en la lista y, a continuación, haga clic en **Aceptar**.

      - Para escribir un nuevo nombre, escriba una dirección de correo electrónico en la casilla **nombres** y, a continuación, seleccione **nombres de casilla** \> **Aceptar**.

7. Para agregar más condiciones, elija **Más opciones y,** a continuación, **seleccione Agregar condición** y seleccione en la lista.

   Por ejemplo, para aplicar la regla solo si  el destinatario está fuera de la organización, seleccione agregar condición y, a continuación, seleccione El destinatario es **externo/interno** Fuera de \> **la organización** \> **Aceptar**.

8. Para habilitar el cifrado sin usar las nuevas funcionalidades de OME, en Hacer lo **siguiente,** seleccione Modificar la seguridad del mensaje Aplicar la versión anterior de  OME y, a \> continuación, elija **Guardar**.

   Si recibe un error de que las licencias de IRM no están habilitadas, no está usando OME heredada.

9. (Opcional) Elija **Agregar acción** para especificar otra acción.

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Usar Exchange Online PowerShell para crear una regla de flujo de correo para cifrar mensajes de correo electrónico sin las nuevas funcionalidades de OME

1. Conéctese a Exchange Online PowerShell. Para obtener más información, vea [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Cree una regla mediante el cmdlet **New-TransportRule** y establezca el _parámetro ApplyOME_ en `$true` .

   Este ejemplo requiere que todos los mensajes de correo electrónico enviados DrToniRamos@hotmail.com deben cifrarse.

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   Donde,

   - El nombre único de la nueva regla es "Encrypt rule for Dr Toni Ramos".
   - El _parámetro SentTo_ especifica los destinatarios del mensaje (identificados por nombre, dirección de correo electrónico, nombre distintivo, etc.). En este ejemplo, el destinatario se identifica mediante la dirección de correo electrónico "DrToniRamos@hotmail.com".
   - El _parámetro SentToScope_ especifica la ubicación de los destinatarios del mensaje. En este ejemplo, el buzón del destinatario está en hotmail y no forma parte de la organización, por lo que se `NotInOrganization` usa el valor.

   Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](/powershell/module/exchange/New-TransportRule).

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Quitar el cifrado de las respuestas de correo electrónico cifradas sin las nuevas funcionalidades de OME

Cuando los usuarios de correo electrónico envían mensajes cifrados, los destinatarios de esos mensajes pueden responder con respuestas cifradas. Puede crear reglas de flujo de correo para quitar automáticamente el cifrado de las respuestas para que los usuarios de correo electrónico de su organización no tengan que iniciar sesión en el portal de cifrado para verlos. Puede usar el EAC o los cmdlets Windows PowerShell para definir estas reglas. Puede descifrar los mensajes que se envían desde dentro de la organización o los mensajes que son respuestas a los mensajes enviados desde dentro de la organización. No se pueden descifrar mensajes cifrados procedentes de fuera de la organización.

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Usar el EAC para crear una regla para quitar el cifrado de las respuestas de correo electrónico cifradas sin las nuevas funcionalidades de OME

1. En un explorador web, con una cuenta de trabajo o escuela a la que se han concedido permisos de administrador, inicie [sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el **icono** Administrador.

3. En el centro Microsoft 365 administración, elija **Centros de administración** \> **Exchange**.

4. En el EAC, vaya a **Flujo de correo** \> **Reglas** y **seleccione Nuevo** icono Nuevo ![ Crear una nueva ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regla**. Para obtener más información acerca del uso del EAC, vea [Exchange centro de administración en Exchange Online](/exchange/exchange-admin-center).

5. En **Nombre**, escriba un nombre para la regla, como Quitar cifrado del correo entrante.

6. In **Apply this rule if** select the conditions where encryption should be removed from messages, such as The recipient is **located** Inside \> **the organization**.

7. En **Hacer lo siguiente,** seleccione **Modificar la seguridad del mensaje** Quitar la versión anterior \> **de OME**.

8. Seleccione **Guardar**.

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Usar Exchange Online PowerShell para crear una regla para quitar el cifrado de las respuestas de correo electrónico cifradas sin las nuevas funcionalidades de OME

1. Conéctese a Exchange Online PowerShell. Para obtener más información, vea [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Cree una regla mediante el cmdlet **New-TransportRule** y establezca el _parámetro RemoveOME_ en `$true` .

   En este ejemplo se quita el cifrado de todo el correo enviado a los destinatarios de la organización.

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   Donde,

   - El nombre único de la nueva regla es "Quitar el cifrado del correo entrante".
   - El _parámetro SentToScope_ especifica la ubicación de los destinatarios del mensaje. En este ejemplo, se usa `InOrganization` el valor, que indica una de las siguientes opciones:
     - El destinatario es un buzón, un usuario de correo, un grupo o una carpeta pública habilitada para correo de la organización.
     - La dirección de correo electrónico del destinatario se encuentra en un dominio aceptado que está configurado como un dominio autoritativo o un dominio de retransmisión interno en la _organización,_ y el mensaje se envió o recibió a través de una conexión autenticada.

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](/powershell/module/exchange/New-TransportRule).

## <a name="sending-viewing-and-replying-to-messages-encrypted-without-the-new-capabilities"></a>Enviar, ver y responder a mensajes cifrados sin las nuevas funcionalidades

Con Cifrado de mensajes de Office 365, los mensajes de correo electrónico se cifran automáticamente, en función de las reglas definidas por el administrador. Un correo electrónico que lleva un mensaje cifrado llega a la Bandeja de entrada del destinatario con un archivo HTML adjunto.
  
Los destinatarios siguen las instrucciones del mensaje para abrir los datos adjuntos y autenticarse mediante una cuenta de Microsoft o un trabajo o escuela asociados con Office 365. Si los destinatarios no tienen ninguna cuenta, se les dirige a crear una cuenta de Microsoft que les permita iniciar sesión para ver el mensaje cifrado. Como alternativa, los destinatarios pueden elegir obtener un código de paso único para ver el mensaje. Después de iniciar sesión o usar un código de paso único, los destinatarios pueden ver el mensaje descifrado y enviar una respuesta cifrada.
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Personalizar mensajes cifrados con Cifrado de mensajes de Office 365

Como administrador Exchange Online y Exchange Online Protection, puede personalizar los mensajes cifrados. Por ejemplo, puede agregar la marca y el logotipo de su empresa, especificar una introducción y agregar texto de declinación de responsabilidades en mensajes cifrados y en el portal donde los destinatarios ven los mensajes cifrados. Con Windows PowerShell cmdlets, puede personalizar los siguientes aspectos de la experiencia de visualización para los destinatarios de mensajes de correo electrónico cifrados:

- Texto introductorio del correo electrónico que contiene el mensaje cifrado

- Texto de declinación de responsabilidades del correo electrónico que contiene el mensaje cifrado

- Texto del portal que aparecerá en el portal de visualización de mensajes

- Logotipo que aparecerá en el mensaje de correo electrónico y el portal de visualización

También puede volver a la apariencia predeterminada en cualquier momento.
  
En el siguiente ejemplo se muestra un logotipo personalizado para ContosoPharma en los datos adjuntos de correo electrónico:

> [!div class="mx-imgBorder"]
> ![Ejemplo de la página de visualización del mensaje cifrado](../media/TA-OME-3attachment2.jpg)
  
**Para personalizar los mensajes de correo electrónico de cifrado y el portal de cifrado con la marca de su organización**
  
1. Conectar usar Exchange Online PowerShell remoto, como se describe en Conectar para Exchange Online [con PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use el cmdlet Set-OMEConfiguration como se describe aquí: [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) o use la tabla siguiente para obtener instrucciones.

   **Opciones de personalización de cifrado**

   | Para personalizar esta característica de la experiencia de cifrado | Use estos Windows PowerShell comandos |
   |:-----|:-----|
   |Texto predeterminado que acompaña a los mensajes de correo electrónico cifrados  <br/> El texto predeterminado aparece encima de las instrucciones para ver mensajes cifrados  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
   |Declaración de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
   |Texto que aparece en la parte superior del portal de visualización de correo cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
   |Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formatos de archivo compatibles: .png, .jpg, .bmp o .tiff  <br/> Tamaño óptimo del archivo de logotipo: menos de 40 KB  <br/> Tamaño óptimo de la imagen del logotipo: 170 x 70 píxeles  <br/> |

**Para quitar personalizaciones de marca de mensajes de correo electrónico de cifrado y el portal de cifrado**
  
1. Conectar usar Exchange Online PowerShell remoto, como se describe en Conectar para Exchange Online [con PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use el cmdlet Set-OMEConfiguration como se describe aquí: [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration). Para quitar las personalizaciones de marca de la organización de los valores DisclaimerText, EmailText y PortalText, establezca el valor en una cadena vacía,  `""` . Para todos los valores de imagen, como Logo, establezca el valor en  `"$null"` .

   **Opciones de personalización de cifrado**

   | Para revertir esta característica de la experiencia de cifrado al texto e imagen predeterminados | Use estos Windows PowerShell comandos |
   |:-----|:-----|
   |Texto predeterminado que acompaña a los mensajes de correo electrónico cifrados  <br/> El texto predeterminado aparece encima de las instrucciones para ver mensajes cifrados  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
   |Declaración de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Ejemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
   |Texto que aparece en la parte superior del portal de visualización de correo cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Ejemplo de reversión al valor predeterminado:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
   |Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Ejemplo de reversión al valor predeterminado:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>Información de servicio para las Cifrado de mensajes de Office 365 anteriores al lanzamiento de las nuevas funcionalidades de OME
<a name="LegacyServiceInfo"> </a>

En la tabla siguiente se proporcionan detalles técnicos para el servicio Cifrado de mensajes de Office 365 antes del lanzamiento de las nuevas funcionalidades de OME.
  
| Detalles del servicio | Descripción |
|:-----|:-----|
|Requisitos de dispositivo de cliente  <br/> |Los mensajes cifrados se pueden ver en cualquier dispositivo de cliente, siempre y cuando los datos adjuntos HTML puedan abrirse en un explorador moderno que admita el envío de formularios.  <br/> |
|Algoritmo de cifrado y compatibilidad con FIPS (Estándar federal de procesamiento de información)  <br/> |El Cifrado de mensajes de Office 365 emplea las mismas claves de cifrado que Microsoft Azure Information Rights Management (IRM) y admite el modo criptográfico 2 (clave de 2048 bits para RSA y de 256 bits para sistemas SHA-1). Para obtener más información acerca de los modos criptográficos subyacentes de IRM, vea [Modos criptográficos de AD RMS](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)).  <br/> |
|Tipos de mensaje admitidos  <br/> |Solo se admite el cifrado de mensajes de Office 365 para los elementos que tienen un identificador de clase de mensaje de **IPM.Note**. Para obtener más información, vea [Tipos de elementos y clases de mensaje](/office/vba/outlook/Concepts/Forms/item-types-and-message-classes).  <br/> |
|Límites de tamaño de mensaje  <br/> |El Cifrado de mensajes de Office 365 es capaz de cifrar mensajes de hasta 25 megabytes. Para obtener más información acerca de los límites de tamaño del [mensaje, vea Exchange Online Limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).  <br/> |
|Exchange Online de retención de correo electrónico  <br/> |Exchange Online no almacena los mensajes cifrados.  <br/> |
|Compatibilidad de idiomas en el cifrado de mensajes de Office 365  <br/> | Office 365 El cifrado de mensajes admite Microsoft 365 idiomas, como se indica a continuación:  <br/>  Los mensajes de correo electrónico entrantes y los archivos HTML adjuntos se localizan en función de la configuración de idioma del remitente.  <br/>  El portal de visualización se localiza en función de la configuración del explorador del destinatario.  <br/>  El cuerpo (contenido) del mensaje cifrado no se localiza.  <br/> |
|Información de privacidad del Portal OME y la aplicación Visor OME  <br/> |El vínculo [Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/privacystatement) proporciona más información sobre el uso de su información privada por parte de Microsoft.  <br/> |

## <a name="frequently-asked-questions-about-legacy-ome"></a>Preguntas más frecuentes sobre la OME heredada
<a name="LegacyServiceInfo"> </a>

¿Tiene preguntas sobre Cifrado de mensajes de Office 365? Aquí encontrará algunas respuestas. Si no encuentra lo que necesita, consulte los foros de [Microsoft Tech Community para Office 365](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365).
  
 **P. Mis usuarios envían mensajes de correo electrónico cifrados a destinatarios fuera de nuestra organización. ¿Hay algo que los destinatarios externos tengan que hacer para leer y responder a los mensajes de correo electrónico cifrados con Cifrado de mensajes de Office 365?**
  
Los destinatarios fuera de la organización que reciben Microsoft 365 mensajes cifrados pueden verlos de dos maneras:
  
- Al iniciar sesión con una cuenta de Microsoft o una cuenta laboral o educativa asociada con Office 365.

- Mediante un código de paso único.

 **P. ¿Microsoft 365 mensajes cifrados en la nube o en servidores microsoft?**
  
No, los mensajes cifrados se mantienen en el sistema de correo electrónico del destinatario y, cuando el destinatario abre el mensaje, se publica temporalmente para su visualización en servidores Microsoft. Pero los mensajes no se almacenan ahí.
  
 **P. ¿Puedo personalizar los mensajes de correo electrónico cifrado con mi marca?**
  
Sí. Puede usar cmdlets de Windows PowerShell para personalizar el texto predeterminado que aparece en la parte superior de los mensajes de correo electrónico cifrados, el texto de aviso de declinación de responsabilidades y el logotipo que quiera usar para el mensaje de correo electrónico y el portal de cifrado. Esta característica ya está disponible en OMEv2. Para más información, consulte [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).
  
 **P. ¿Requiere el servicio una licencia para cada usuario de la organización?**
  
Se requiere una licencia para cada usuario de la organización que envíe correo electrónico cifrado.
  
 **P. ¿Requieren los destinatarios externos suscripciones?**
  
No, los destinatarios externos no requieren una suscripción para leer o responder los mensajes cifrados.
  
 **P. ¿En Cifrado de mensajes de Office 365 es diferente de Rights Management Services (RMS)?**
  
RMS proporciona funcionalidades de Information Rights Protection para los correos electrónicos internos de una organización proporcionando plantillas integradas, como: No reenviar y Confidencial de la empresa. El cifrado de mensajes de Office 365 es compatible con el cifrado para los mensajes de correo electrónico que se envían a destinatarios externos, así como destinatarios internos.
  
 **P. ¿En Cifrado de mensajes de Office 365 es diferente de S/MIME?**
  
S/MIME es básicamente una tecnología de cifrado del lado cliente y requiere la administración de certificados complicados y la publicación de infraestructura. Cifrado de mensajes de Office 365 reglas de flujo de correo (también conocidas como reglas de transporte) y no depende de la publicación de certificados.
  
 **P. ¿Puedo leer los mensajes cifrados en dispositivos móviles?**
  
Sí, puedes ver mensajes en Android e iOS descargando las aplicaciones visor de OME desde la Tienda Google Play y la Tienda de aplicaciones de Apple. Abra los datos adjuntos en formato HTML en la aplicación del Visor de OME y, a continuación, siga las instrucciones para abrir el mensaje cifrado. Para otros dispositivos móviles, puede abrir los datos adjuntos en formato HTML siempre que el cliente de correo permita la publicación de formularios.
  
 **P. ¿Se cifran las respuestas y los mensajes reenviados?**
  
Sí. Las respuestas se siguen cifrando durante todo el período de la conversación.
  
 **P. ¿Cifrado de mensajes de Office 365 proporciona localización?**
  
El correo electrónico entrante y el contenido HTML se localiza según la configuración de correo electrónico del remitente. El portal de visualización se localiza según la configuración del explorador del destinatario. Sin embargo, el cuerpo (contenido) del mensaje cifrado no se localiza.
  
 **P. ¿Qué método de cifrado se usa para Cifrado de mensajes de Office 365?**
  
Cifrado de mensajes de Office 365 Rights Management Services (RMS) como su infraestructura de cifrado. El método de cifrado utilizado depende de dónde obtiene las claves de RMS utilizadas para cifrar y descifrar mensajes.
  
- Si usa Microsoft Azure RMS para obtener las claves, se usa el modo criptográfico 2. El modo criptográfico 2 es una implementación criptográfica de AD RMS actualizada y mejorada. Es compatible con RSA 2048 para firma y cifrado, y admite SHA-256 para firma.

- Si usa Active Directory (AD) RMS para obtener las claves, se utiliza el modo criptográfico 1 o el modo criptográfico 2. El método empleado depende de la implementación local de AD RMS. El modo criptográfico 1 es la implementación criptográfica original de AD RMS. Es compatible con RSA 1024 para firma y cifrado, y admite SHA-1 para firma. Este modo sigue siendo compatible con todas las versiones actuales de RMS.

Para obtener más información, [vea Modos criptográficos de AD RMS](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)).
  
**P. ¿Por qué algunos mensajes cifrados dicen que proceden de** Office365@messaging.microsoft.com?
  
Cuando se envía una respuesta cifrada desde el portal de cifrado o a través de la aplicación del Visor de OME, la dirección de correo electrónico de envío se establece en Office365@messaging.microsoft.com porque el mensaje cifrado se envía a través de un extremo de Microsoft. Esto ayuda a evitar que los mensajes cifrados se marquen como correo no deseado. El nombre mostrado en el correo electrónico y la dirección del portal de cifrado no se modifican a causa de este etiquetado. Además, este etiquetado solo se aplica a los mensajes enviados a través del portal, no a través de cualquier otro cliente de correo electrónico.
  
 **P. Soy un suscriptor Exchange cifrado hospedado (EHE). ¿Dónde puedo obtener más información sobre la actualización a Cifrado de mensajes de Office 365?**
  
Todos los clientes de EHE se han actualizado a Cifrado de mensajes de Office 365. Para obtener más información, visite [el centro Exchange de actualización](../security/defender-365-security/exchange-online-protection-overview.md)de cifrado hospedado .
  
 **P. ¿Necesito abrir direcciones URL, direcciones IP o puertos en el firewall de mi organización para admitir Cifrado de mensajes de Office 365?**
  
Sí. Debe agregar direcciones URL para Exchange Online para que la lista de permitidos de la organización habilite la autenticación de los mensajes cifrados por parte del servicio de cifrado de mensajes de Office 365. Para obtener una lista de Exchange Online direcciones URL, vea Microsoft 365 direcciones URL e [intervalos de direcciones IP](../enterprise/urls-and-ip-address-ranges.md).
  
 **P. ¿A cuántos destinatarios puedo enviar un Microsoft 365 cifrado?**
  
El límite de destinatarios es de 500 destinatarios por mensaje o, cuando se combina después de la expansión de la lista de distribución, 11.980 caracteres en el campo **Para** del mensaje, lo que sea primero.
  
 **P. ¿Es posible revocar un mensaje enviado a un destinatario concreto?**
  
No. No puede revocar un mensaje a una persona determinada después de que se envíe.
  
 **P. ¿Puedo ver un informe de los mensajes cifrados que se han recibido y leído?**
  
No hay un informe que muestre si se ha visto un mensaje cifrado, pero hay informes Microsoft 365 disponibles que puede aprovechar para determinar el número de mensajes que coinciden con una regla de flujo de correo específica (también conocida como regla de transporte), por ejemplo.
  
 **P. ¿Qué hace Microsoft con la información que proporciono a través del Portal OME y la aplicación Visor OME?**
  
La [Office 365 privacidad del Portal](https://privacy.microsoft.com/privacystatement) de cifrado de mensajería proporciona información detallada sobre lo que Microsoft hace y no hace con su información privada.

**P. ¿Qué hago si no recibo el código de paso de una sola vez después de solicitarlo?**

En primer lugar, compruebe la carpeta de correo no deseado o correo no deseado en el cliente de correo electrónico. La configuración de DKIM y DMARC para su organización puede hacer que estos correos electrónicos terminen filtrados como correo no deseado.

A continuación, compruebe la cuarentena en el Centro de seguridad & cumplimiento. A menudo, los mensajes que contienen un código de paso único, especialmente los primeros que recibe la organización, terminan en cuarentena.