---
title: Agregar la marca de organización a los mensajes cifrados
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Aplique la personalización de marca de su organización a los mensajes de correo electrónico cifrados de la organización y al contenido del portal de cifrado.
ms.openlocfilehash: 86636b319151a96e9ec827f85cc943282c30f63c
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679114"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Agregar la marca de su organización a los mensajes cifrados

Como administrador de Exchange online o Exchange Online Protection, puede aplicar la personalización de marca de la empresa para personalizar la apariencia de los mensajes de correo electrónico de Microsoft 365 para cifrado de mensajes empresariales y el contenido del portal de cifrado. Con los cmdlets de Windows PowerShell Get-OMEConfiguration y set-OMEConfiguration, puede personalizar los siguientes aspectos de la experiencia de visualización para los destinatarios de los mensajes de correo electrónico cifrados:
  
- Texto de introducción del correo electrónico que contiene el mensaje cifrado

- Texto de declinación de responsabilidades del correo electrónico que contiene el mensaje cifrado

- Dirección URL de la declaración de privacidad de la organización

- Texto que aparece en el portal de OME

- Logotipo que aparece en el portal de mensajes de correo electrónico y OME, o bien si se va a usar un logotipo

- Color de fondo en el portal de mensajes de correo electrónico y OME

También puede volver a la apariencia predeterminada en cualquier momento.

Si desea tener más control, puede usar el cifrado de mensajes avanzado de Office 365 y crear varias plantillas para los mensajes de correo electrónico cifrados que se originan en la organización. Mediante el uso de estas plantillas, puede controlar algo más que la apariencia de los mensajes de correo electrónico, pero también controlar partes de la experiencia del usuario final. Por ejemplo, puede especificar si los destinatarios de correo a los que se aplica esta plantilla y si usan cuentas de Google, Yahoo y Microsoft pueden usar estas cuentas para iniciar sesión en el portal de cifrado de mensajes de Office 365. Puede usar plantillas para cumplir varios casos de uso, como:

- Plantillas para cada departamento, como finanzas, ventas, etc.

- Plantillas para diferentes productos

- Plantillas para diferentes regiones geográficas o países

- Si desea permitir que se revoquen los mensajes de correo electrónico

- Si desea que los mensajes enviados a destinatarios externos expiren después de un número determinado de días.

Una vez que haya creado las plantillas, puede aplicarlas a los correos electrónicos cifrados mediante las reglas de flujo de correo de Exchange. Si tiene el cifrado de mensajes avanzado de Office 365, puede revocar cualquier correo electrónico de personalización de marca mediante estas plantillas.

## <a name="work-with-ome-branding-templates"></a>Trabajar con plantillas de personalización de marca OME

Puede modificar varias características dentro de una plantilla de personalización de marca. Puede modificar la plantilla predeterminada, pero no quitarla. Si tiene cifrado de mensajes avanzado, también puede crear, modificar y quitar plantillas personalizadas. Use Windows PowerShell para trabajar con una plantilla de personalización de marca cada vez. Necesitará una cuenta profesional o educativa que tenga permisos de administrador global en su organización para usar estos cmdlets.

- [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) -modificar la plantilla de personalización de marca predeterminada o una plantilla de personalización de marca personalizada creada.
- [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) -crea una nueva plantilla de personalización de marca, solo cifrado de mensajes avanzado.
- [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) -quitar una plantilla de personalización de marca personalizada, sólo el cifrado de mensajes avanzado. La plantilla de personalización de marca predeterminada no se puede eliminar.
  
## <a name="modify-an-ome-branding-template"></a>Modificación de una plantilla de personalización de marca OME

Use Windows PowerShell para modificar una plantilla de personalización de marca a la vez. Si tiene cifrado de mensajes avanzado, también puede crear, modificar y quitar plantillas personalizadas.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Modifique la plantilla con el cmdlet Set-OMEConfiguration como se describe en [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) o use el siguiente gráfico y tabla para obtener instrucciones.

![Elementos de correo electrónico personalizables](../media/ome-template-breakout.png)

|**Para personalizar esta característica de la experiencia de cifrado**|**Use estos comandos**|
|:-----|:-----|
|Color de fondo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> Para obtener más información acerca de los colores de fondo, vea la sección [colores de fondo](#background-color-reference) más adelante en este tema.|
|Logotipo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formatos de archivo compatibles: .png, .jpg, .bmp o .tiff  <br/> Tamaño óptimo del archivo de logotipo: menos de 40 KB  <br/> Tamaño óptimo de la imagen de logotipo: 170 píxeles. Si la imagen supera estas dimensiones, el servicio cambia el tamaño del logotipo para mostrarlo en el portal. El servicio no modifica el archivo gráfico en sí. Para obtener los mejores resultados, use el tamaño óptimo.|
|Texto junto al nombre y la dirección de correo electrónico del remitente|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Texto que aparece en el botón "leer mensaje"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Texto que aparece debajo del botón "leer mensaje"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|Dirección URL para el vínculo de la declaración de privacidad|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|Declaración de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Texto que aparece en la parte superior del portal de visualización de correo cifrado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Para habilitar o deshabilitar la autenticación con un código de paso único para esta plantilla personalizada|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **Ejemplos:** <br/>Para habilitar los códigos de acceso de una sola vez para esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Para deshabilitar los códigos de acceso de un solo uso para esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Para habilitar o deshabilitar la autenticación con identidades de Microsoft, Google o Yahoo para esta plantilla personalizada|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **Ejemplos:** <br/>Para habilitar identificadores sociales para esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Para deshabilitar los identificadores sociales de esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Crear una plantilla de personalización de marca OME (cifrado de mensajes avanzado)

Si tiene el cifrado de mensajes avanzado de Office 365, puede crear plantillas de personalización de marca personalizadas para su organización con el cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) . Una vez que haya creado la plantilla, modifique la plantilla mediante el cmdlet Set-OMEConfiguration como se describe en [Modify an OME branding template](#modify-an-ome-branding-template). Puede crear varias plantillas.

Para crear una nueva plantilla de personalización de marca personalizada:

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Use el cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) para crear una nueva plantilla.

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Devolver la plantilla de personalización de marca predeterminada a sus valores originales

Para quitar todas las modificaciones de la plantilla predeterminada, incluidas las personalizaciones de marca, etc., siga estos pasos:
  
1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Use el cmdlet **set-OMEConfiguration** como se describe en [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration). Para quitar las personalizaciones de marca de la organización de los valores de DisclaimerText, EmailText y PortalText, establezca el valor en una cadena vacía `""` . Para todos los valores de imagen, como el logotipo, establezca el valor en `"$null"` .

   En la tabla siguiente se describen los valores predeterminados de la opción de personalización de cifrado.

   **Para revertir esta característica de la experiencia de cifrado de nuevo a la imagen y el texto predeterminados**|**Use estos comandos**|
   |:-----|:-----|
   |Texto predeterminado que acompaña a los mensajes de correo electrónico cifrados  <br/> El texto predeterminado aparece por encima de las instrucciones para ver los mensajes cifrados|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Declaración de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Texto que aparece en la parte superior del portal de visualización de correo cifrado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **Ejemplo de volver a su valor predeterminado:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logotipo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **Ejemplo de volver a su valor predeterminado:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Color de fondo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **Ejemplo de volver a su valor predeterminado:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Quitar una plantilla de personalización de marca personalizada (cifrado de mensajes avanzado)

Solo puede quitar o eliminar las plantillas de personalización de marca que haya hecho. No puede quitar la plantilla de personalización de marca predeterminada.

Para quitar una plantilla de personalización de marca personalizada:
  
1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Use el cmdlet **Remove-OMEConfiguration** de la siguiente manera:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   For example,

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Para obtener más información, vea [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Crear una regla de flujo de correo de Exchange que aplique la personalización de marca personalizada a los correos electrónicos cifrados

Una vez que haya modificado la plantilla predeterminada o creado nuevas plantillas de personalización de marca, puede crear reglas de flujo de correo de Exchange para aplicar la personalización de marca personalizada según ciertas condiciones. Dicha regla aplicará la personalización de marca personalizada en los siguientes escenarios:

- Si el usuario final cifró manualmente el correo electrónico desde los clientes de Outlook o Outlook en la web (anteriormente conocido como Outlook Web App)

- Si el correo electrónico se cifró automáticamente mediante una regla de flujo de correo de Exchange o una directiva de prevención de pérdida de datos

Para obtener información sobre cómo crear una regla de flujo de correo de Exchange que aplique cifrado, vea [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. En un explorador Web, con una cuenta profesional o educativa a la que se le han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administración** .

3. En el centro de administración de Microsoft 365, elija centro de **Administración** , \> **Exchange**.

4. En el EAC, vaya a reglas de **flujo de correo** \> **Rules** y seleccione **nuevo** icono nuevo para ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **crear una nueva regla**. Para obtener más información acerca del uso de EAC, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. En **nombre**, escriba un nombre para la regla, como la personalización de marca del Departamento de ventas.

6. En **aplicar esta regla si**, seleccione la condición en que **el remitente se encuentra dentro de la organización** , así como las demás condiciones que desee en la lista de condiciones disponibles. Por ejemplo, es posible que desee aplicar una plantilla de personalización de marca determinada a:

   - Todos los mensajes de correo electrónico cifrados enviados desde miembros del Departamento de finanzas
   - Mensajes de correo electrónico cifrados enviados con una palabra clave determinada, como "external" o "Partner"
   - Mensajes de correo electrónico cifrados enviados a un dominio en particular

7. En **hacer lo siguiente**, seleccione **modificar la seguridad de mensajes**aplicar personalización de  >  **marca personalizada a los mensajes OME**. A continuación, en la lista desplegable, seleccione una plantilla de personalización de marca de las que ha creado o modificado.

8. Opcional Si desea que la regla de flujo de correo aplique el cifrado además de la personalización de marca, **haga lo siguiente**, seleccione **modificar la seguridad de los mensajes**y, a continuación, elija **aplicar el cifrado de mensajes de Office 365 y la protección de derechos**. Seleccione una plantilla RMS de la lista, elija **Guardar**y, después, haga clic en **Aceptar**.
  
   La lista de plantillas incluye todas las plantillas y opciones predeterminadas, así como las plantillas personalizadas que haya creado para su uso por parte de Office 365. Si la lista está vacía, asegúrese de haber configurado el cifrado de mensajes de Office 365 con las nuevas funciones, tal como se describe en [set up New Office 365 Message Encryption Capabilities](set-up-new-message-encryption-capabilities.md). Para obtener información sobre las plantillas predeterminadas, vea [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obtener información sobre la opción no **reenviar** , vea la [opción no reenviar para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información sobre la opción **solo cifrar** , vea la [opción cifrar solo para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Elija **Agregar acción** si desea especificar otra acción.

## <a name="background-color-reference"></a>Referencia de color de fondo

Los nombres de color que puede usar para el color de fondo son limitados. En lugar de un nombre de color, puede usar un valor de código hexadecimal (#RRGGBB). Puede usar un valor de código hexadecimal que corresponda a un nombre de color o puede usar un valor de código hexadecimal personalizado. Asegúrese de incluir el valor de código hexadecimal entre comillas (por ejemplo, `"#f0f8ff"` ).

En la tabla siguiente se describen los nombres de color de fondo disponibles y sus valores de código hexadecimal correspondientes.

|||
|---|---|
|**Nombre del color**|**Código de color**|
|aliceblue|#f0f8ff|
|antiquewhite|#faebd7|
|aguamarina|#00ffff|
|aguamarina|#7fffd4|
|Azure|#f0ffff|
|beige|#f5f5dc|
|bisque|#ffe4c4|
|black|#000000|
|blanchedalmond|#ffebcd|
|azul|#0000ff|
|blueviolet|#8a2be2|
|Ruiz|#a52a2a|
|burlywood|#deb887|
|cadetblue|#5f9ea0|
|chartreuse|#7fff00|
|chocolate|#d2691e|
|Coral|#ff7f50|
|cornflowerblue|#6495ed|
|cornsilk|#fff8dc|
|rojo|#dc143c|
|azulado|#00ffff|
|darkblue|#00008b|
|darkcyan|#008b8b|
|darkgoldenrod|#b8860b|
|darkgray|#a9a9a9|
|darkgreen|#006400|
|darkkhaki|#bdb76b|
|darkmagenta|#8b008b|
|darkolivegreen|#556b2f|
|darkorange|#ff8c00|
|darkorchid|#9932cc|
|darkred|#8b0000|
|darksalmon|#e9967a|
|darkseagreen|#8fbc8f|
|darkslateblue|#483d8b|
|darkslategray|#2f4f4f|
|darkturquoise|#00ced1|
|darkviolet|#9400d3|
|deeppink|#ff1493|
|deepskyblue|#00bfff|
|dimgray|#696969|
|dodgerblue|#1e90ff|
|firebrick|#b22222|
|floralwhite|#fffaf0|
|forestgreen|#228b22|
|fucsia|#ff00ff|
|gainsboro|#dcdcdc|
|ghostwhite|#f8f8ff|
|máximo|#ffd700|
|ocre|#daa520|
|neutro|#808080|
|verde|#008000|
|greenyellow|#adff2f|
|Rocío|#f0fff0|
|hotpink|#ff69b4|
|indianred|#cd5c5c|
|Indigo|#4b0082|
|d'ivoire|#fffff0|
|caqui|#f0e68c|
|lavanda|#e6e6fa|
|lavenderblush|#fff0f5|
|lawngreen|#7cfc00|
|lemonchiffon|#fffacd|
|lightblue|#add8e6|
|lightcoral|#f08080|
|lightcyan|#e0ffff|
|lightgoldenrodyellow|#fafad2|
|lightgray|#d3d3d3|
|lightgrey|#d3d3d3|
|lightgreen|#90ee90|
|lightpink|#ffb6c1|
|lightsalmon|#ffa07a|
|lightseagreen|#20b2aa|
|lightskyblue|#87cefa|
|lightslategray|#778899|
|lightsteelblue|#b0c4de|
|lightyellow|#ffffe0|
|cal|#00ff00|
|limegreen|#32cd32|
|cama|#faf0e6|
|ese|#ff00ff|
|granate|#800000|
|mediumaquamarine|#66cdaa|
|mediumblue|#0000cd|
|mediumorchid|#ba55d3|
|mediumpurple|#9370db|
|mediumseagreen|#3cb371|
|mediumslateblue|#7b68ee|
|mediumspringgreen|#00fa9a|
|mediumturquoise|#48d1cc|
|mediumvioletred|#c71585|
|midnightblue|#191970|
|mintcream|#f5fffa|
|mistyrose|#ffe4e1|
|moccasin|#ffe4b5|
|navajowhite|#ffdead|
|azul marino|#000080|
|oldlace|#fdf5e6|
|mesa|#808000|
|olivedrab|#6b8e23|
|naranja|#ffa500|
|orangered|#ff4500|
|Orquídea|#da70d6|
|palegoldenrod|#eee8aa|
|palegreen|#98fb98|
|paleturquoise|#afeeee|
|palevioletred|#db7093|
|papayawhip|#ffefd5|
|peachpuff|#ffdab9|
|Perú|#cd853f|
|Rosas|#ffc0cb|
|ciruela|#dda0dd|
|powderblue|#b0e0e6|
|púrpura|#800080|
|rojo|#ff0000|
|rosybrown|#bc8f8f|
|royalblue|#4169e1|
|saddlebrown|#8b4513|
|salmón|#fa8072|
|sandybrown|#f4a460|
|seagreen|
|seashell|#fff5ee|
|sienna|#a0522d|
|duplica|#c0c0c0|
|skyblue|#87ceeb|
|slateblue|#6a5acd|
|slategray|#708090|
|muñeco|#fffafa|
|springgreen|#00ff7f|
|steelblue|#4682b4|
|bronce|#d2b48c|
|verde|#008080|
|thistle|#d8bfd8|
|espontánea|#ff6347|
|turquesa|#40e0d0|
|violáceo|#ee82ee|
|trigo|#f5deb3|
|white|#ffffff|
|whitesmoke|#f5f5f5|
|amarillo|#ffff00|
|yellowgreen|#9acd32|
