---
title: Adición de la marca a mensajes cifrados
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 5/12/2022
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
- admindeeplinkMAC
- admindeeplinkEXCHANGE
description: Obtenga información sobre cómo Office 365 administradores globales pueden aplicar la personalización de marca de su organización a mensajes de correo electrónico cifrados & contenido del portal de cifrado.
ms.openlocfilehash: c8806f3f52fe5c76ff0e318a13789f580d4e31e2
ms.sourcegitcommit: 4e7ff69f4d7d27c2d419f763cfcb069e3b0d0d9f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "65403346"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>Adición de la marca de la organización a los mensajes cifrados de cifrado de mensajes de Microsoft 365 para empresas

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Puede aplicar la personalización de marca de la empresa para personalizar el aspecto de los mensajes de correo electrónico de la organización y el portal de cifrado. Tendrá que aplicar permisos de administrador global a su cuenta profesional o educativa antes de empezar. Una vez que tenga estos permisos, use los cmdlets Get-OMEConfiguration y Set-OMEConfiguration Windows PowerShell para personalizar estas partes de los mensajes de correo electrónico cifrados:

- Texto introductorio
- Disclaimer text
- Dirección URL de la declaración de privacidad de su organización
- Texto en el portal de OME
- Logotipo que aparece en el mensaje de correo electrónico y en el portal de OME, o si se va a usar un logotipo en absoluto
- Color de fondo en el mensaje de correo electrónico y el portal de OME

También puede volver a la apariencia predeterminada en cualquier momento.

Si desea tener más control, use Microsoft Purview Cifrado avanzado de mensajes para crear varias plantillas para correos electrónicos cifrados que se originen en su organización. Use estas plantillas para controlar partes de la experiencia del usuario final. Por ejemplo, especifique si los destinatarios pueden usar cuentas de Google, Yahoo y Microsoft para iniciar sesión en el portal de cifrado. Use plantillas para cumplir varios casos de uso, como:

- Departamentos individuales, como Finanzas, Ventas, etc.
- Diferentes productos
- Diferentes regiones geográficas o países
- Si desea permitir que se revoquen los correos electrónicos
- Si desea que los correos electrónicos enviados a destinatarios externos expiren después de un número especificado de días.

Una vez creadas las plantillas, puede aplicarlas a correos electrónicos cifrados mediante Exchange reglas de flujo de correo. Si tiene Microsoft Purview Cifrado avanzado de mensajes, puede revocar cualquier correo electrónico que haya marcado mediante estas plantillas.

## <a name="work-with-ome-branding-templates"></a>Trabajar con plantillas de personalización de marca de OME

Puede modificar varias características dentro de una plantilla de personalización de marca. Puede modificar, pero no quitar, la plantilla predeterminada. Si tiene Cifrado avanzado de mensajes, también puede crear, modificar y quitar plantillas personalizadas. Use Windows PowerShell para trabajar con una plantilla de personalización de marca a la vez.

- [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) : modifique la plantilla de personalización de marca predeterminada o una plantilla de personalización de marca personalizada que ha creado.
- [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) : cree una nueva plantilla de personalización de marca, solo cifrado avanzado de mensajes.
- [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) : quite una plantilla de personalización de marca personalizada, solo cifrado de mensajes avanzado. No puede eliminar la plantilla de personalización de marca predeterminada.

## <a name="modify-an-ome-branding-template"></a>Modificación de una plantilla de personalización de marca de OME

Use Windows PowerShell para modificar una plantilla de personalización de marca a la vez. Si tiene Cifrado avanzado de mensajes, también puede crear, modificar y quitar plantillas personalizadas.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use el cmdlet Set-OMEConfiguration como se describe en [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) o use el siguiente gráfico y tabla para obtener instrucciones.

![Elementos de correo electrónico personalizables.](../media/ome-template-breakout.png)

<br>

****

|**Para personalizar esta característica de la experiencia de cifrado**|**Uso de estos comandos**|
|---|---|
|Color de fondo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <p> **Ejemplo:** <p> `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <p> Para obtener más información sobre los colores de fondo, consulte la sección [Colores de fondo](#background-color-reference) más adelante en este artículo.|
|Logotipo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <p> **Ejemplo:** <p> `Set-OMEConfiguration -Identity "Branding Template 1" -Image ([System.IO.File]::ReadAllBytes('C:\Temp\contosologo.png'))` <p> Formatos de archivo compatibles: .png, .jpg, .bmp o .tiff <p> Tamaño óptimo del archivo de logotipo: menos de 40 KB <p> Tamaño óptimo de la imagen del logotipo: 170 x 70 píxeles. Si la imagen supera estas dimensiones, el servicio cambia el tamaño del logotipo para que se muestre en el portal. El servicio no modifica el propio archivo gráfico. Para obtener mejores resultados, use el tamaño óptimo.|
|Texto junto al nombre y la dirección de correo electrónico del remitente|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <p> **Ejemplo:** <p> `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Texto que aparece en el botón "Leer mensaje"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <p> **Ejemplo:** <p> `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Texto que aparece debajo del botón "Leer mensaje"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <p> **Ejemplo:** <p> `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|Dirección URL del vínculo Declaración de privacidad|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <p> **Ejemplo:** <p> `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|Declaración de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <p> **Ejemplo:** <p> `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Texto que aparece en la parte superior del portal de visualización de correo cifrado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <p> **Ejemplo:** <p> `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Para habilitar o deshabilitar la autenticación con un código de paso único para esta plantilla personalizada|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <p> **Ejemplos:** <br/>Para habilitar códigos de acceso únicos para esta plantilla personalizada <p> `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <p> Para deshabilitar códigos de acceso únicos para esta plantilla personalizada <p> `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Para habilitar o deshabilitar la autenticación con identidades de Microsoft, Google o Yahoo para esta plantilla personalizada|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <p> **Ejemplos:** <br/>Para habilitar identificadores sociales para esta plantilla personalizada <p> `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <p> Para deshabilitar los identificadores sociales de esta plantilla personalizada <p> `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|
|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Creación de una plantilla de personalización de marca de OME (cifrado avanzado de mensajes)

Si tiene Microsoft Purview Cifrado avanzado de mensajes, puede crear plantillas de personalización de marca personalizadas para su organización mediante el cmdlet [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration). Una vez que haya creado la plantilla, modifique la plantilla mediante el cmdlet Set-OMEConfiguration como se describe en [Modificar una plantilla de personalización de marca de OME](#modify-an-ome-branding-template). Puede crear varias plantillas.

Para crear una nueva plantilla de personalización de marca personalizada:

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use el cmdlet [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) para crear una plantilla.

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   Por ejemplo,

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Devolver la plantilla de personalización de marca predeterminada a sus valores originales

Para quitar todas las modificaciones de la plantilla predeterminada, incluidas las personalizaciones de marca, etc., complete estos pasos:

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use el cmdlet **Set-OMEConfiguration** como se describe en [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration). Para quitar las personalizaciones de marca de la organización de los valores DisclaimerText, EmailText y PortalText, establezca el valor en una cadena vacía, `""`. Para todos los valores de imagen, como Logo, establezca el valor `"$null"`en .

   En la tabla siguiente se describe el valor predeterminado de la opción de personalización de cifrado.

   <br>

   ****

   |Para revertir esta característica de la experiencia de cifrado al texto e imagen predeterminados|Uso de estos comandos|
   |:-----|:-----|
   |Texto predeterminado que viene con mensajes de correo electrónico cifrados. El texto predeterminado aparece encima de las instrucciones para ver los mensajes cifrados|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <p> **Ejemplo:** <p> `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Declaración de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <p> **Ejemplo:** <p> `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Texto que aparece en la parte superior del portal de visualización de correo cifrado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <p> **Ejemplo de reversión al valor predeterminado:** <p> `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logotipo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <p> **Ejemplo de reversión al valor predeterminado:** <p> `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Color de fondo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <p> **Ejemplo de reversión al valor predeterminado:** <p> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Quitar una plantilla de personalización de marca personalizada (cifrado avanzado de mensajes)

Solo puede quitar o eliminar plantillas de personalización de marca que haya realizado. No se puede quitar la plantilla de personalización de marca predeterminada.

Para quitar una plantilla de personalización de marca personalizada:

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use el cmdlet **Remove-OMEConfiguration** de la siguiente manera:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   Por ejemplo,

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Para obtener más información, vea [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Cree una regla de flujo de correo Exchange que aplique la personalización de marca a los correos electrónicos cifrados.

> [!IMPORTANT]
> Las aplicaciones de terceros que examinan y modifican el correo pueden impedir que la personalización de marca de OME se aplique correctamente.

Después de modificar la plantilla predeterminada o de crear nuevas plantillas de personalización de marca, puede crear Exchange reglas de flujo de correo para aplicar la personalización de marca personalizada en función de determinadas condiciones. Lo más importante es que el correo electrónico debe cifrarse. Esta regla aplicará personalización de marca en los siguientes escenarios:

- Si el usuario final cifró manualmente el correo electrónico mediante Outlook o Outlook en la Web, anteriormente Outlook Web App
- Si el correo electrónico se cifró automáticamente mediante una regla de flujo de correo Exchange o una directiva de Prevención de pérdida de datos de Microsoft Purview

Para asegurarse de que Cifrado de mensajes de Microsoft Purview aplica la personalización de marca, configure una regla de flujo de correo para cifrar los mensajes de correo electrónico. La prioridad de la regla de cifrado debe ser mayor que la regla de personalización de marca para que la regla de cifrado se procese primero. De forma predeterminada, si crea la regla de cifrado antes de la regla de personalización de marca, la regla de cifrado tendrá una prioridad mayor. Para obtener información sobre cómo crear una regla de flujo de correo Exchange que aplique el cifrado, consulte [Definición de reglas de flujo de correo para cifrar los mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md). Para obtener información sobre cómo establecer la prioridad de una regla de flujo de correo, consulte [Administrar reglas de flujo de correo](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#set-the-priority-of-a-mail-flow-rule).

1. En un explorador web, con una cuenta profesional o educativa a la que se hayan concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administrador** .

3. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, elija **Centros** \> de administración <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">**Exchange**</a>.

4. En el EAC, vaya a **Reglas** de **flujo** \> de correo y seleccione **Nuevo** ![icono nuevo.](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**Cree una nueva regla**. Para obtener más información sobre el uso del EAC, consulte [Exchange centro de administración en Exchange Online](/exchange/exchange-admin-center).

5. En **Nombre**, escriba un nombre para la regla, como Personalización de marca para el departamento de ventas.

6. En **Aplicar esta regla si**, seleccione la condición **El remitente se encuentra dentro de la organización** y otras condiciones que desee en la lista de condiciones disponibles. Por ejemplo, es posible que quiera aplicar una plantilla de personalización de marca determinada a:

   - Todos los correos electrónicos cifrados enviados desde miembros del departamento financiero
   - Mensajes de correo electrónico cifrados enviados con una palabra clave determinada, como "External" o "Partner".
   - Correos electrónicos cifrados enviados a un dominio determinado

7. Si ya ha definido una regla de flujo de correo para aplicar el cifrado, omita este paso. De lo contrario, para configurar la regla de flujo de correo para aplicar el cifrado, en **Haga lo siguiente**, seleccione **Modificar la seguridad del mensaje** y, a continuación, elija **Aplicar Office 365 cifrado de mensajes y protección de derechos**. Seleccione una plantilla rms de la lista y, a continuación, elija **agregar acción**.

   La lista de plantillas incluye las plantillas y opciones predeterminadas y las plantillas personalizadas que cree. Si la lista está vacía, asegúrese de que ha configurado Cifrado de mensajes de Microsoft Purview. Para obtener instrucciones, consulte [Configuración de Cifrado de mensajes de Microsoft Purview](set-up-new-message-encryption-capabilities.md). Para obtener información sobre las plantillas predeterminadas, consulte [Configuración y administración de plantillas para Azure Information Protection](/information-protection/deploy-use/configure-policy-templates). Para obtener información sobre la opción **No reenviar** , vea [No reenviar opción para correos electrónicos](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información sobre la opción **cifrar solo** , vea [Opción Cifrar solo para correos electrónicos](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).
   
8. En **Haga lo siguiente**, seleccione **Modificar la seguridad** \> del mensaje **Aplicar personalización de marca a los mensajes de OME**. A continuación, en la lista desplegable, seleccione una plantilla de personalización de marca.

   Elija **Agregar acción** si desea especificar otra acción, o bien elija **Guardar** y, a continuación, elija **Aceptar**.

## <a name="background-color-reference"></a>Referencia de color de fondo

Los nombres de color que puede usar para el color de fondo son limitados. En lugar de un nombre de color, puede usar un valor de código hexadecimal (`#RRGGBB`). Puede usar un valor de código hexadecimal que corresponda a un nombre de color o puede usar un valor de código hexadecimal personalizado. Asegúrese de incluir el valor de código hexadecimal entre comillas (por ejemplo, `"#f0f8ff"`).

Los nombres de color de fondo disponibles y sus valores de código hexadecimal correspondientes se describen en la tabla siguiente.

|**Nombre del color**|**Código de color**|
|---|---|
|`aliceblue`|#f0f8ff|
|`antiquewhite`|#faebd7|
|`aqua`|#00ffff|
|`aquamarine`|#7fffd4|
|`azure`|#f0ffff|
|`beige`|#f5f5dc|
|`bisque`|#ffe4c4|
|`black`|#000000|
|`blanchedalmond`|#ffebcd|
|`blue`|#0000ff|
|`blueviolet`|#8a2be2|
|`brown`|#a52a2a|
|`burlywood`|#deb887|
|`cadetblue`|#5f9ea0|
|`chartreuse`|#7fff00|
|`chocolate`|#d2691e|
|`coral`|#ff7f50|
|`cornflowerblue`|#6495ed|
|`cornsilk`|#fff8dc|
|`crimson`|#dc143c|
|`cyan`|#00ffff|
|`darkblue`|#00008b|
|`darkcyan`|#008b8b|
|`darkgoldenrod`|#b8860b|
|`darkgray`|#a9a9a9|
|`darkgreen`|#006400|
|`darkkhaki`|#bdb76b|
|`darkmagenta`|#8b008b|
|`darkolivegreen`|#556b2f|
|`darkorange`|#ff8c00|
|`darkorchid`|#9932cc|
|`darkred`|#8b0000|
|`darksalmon`|#e9967a|
|`darkseagreen`|#8fbc8f|
|`darkslateblue`|#483d8b|
|`darkslategray`|#2f4f4f|
|`darkturquoise`|#00ced1|
|`darkviolet`|#9400d3|
|`deeppink`|#ff1493|
|`deepskyblue`|#00bfff|
|`dimgray`|#696969|
|`dodgerblue`|#1e90ff|
|`firebrick`|#b22222|
|`floralwhite`|#fffaf0|
|`forestgreen`|#228b22|
|`fuchsia`|#ff00ff|
|`gainsboro`|#dcdcdc|
|`ghostwhite`|#f8f8ff|
|`gold`|#ffd700|
|`goldenrod`|#daa520|
|`gray`|#808080|
|`green`|#008000|
|`greenyellow`|#adff2f|
|`honeydew`|#f0fff0|
|`hotpink`|#ff69b4|
|`indianred`|#cd5c5c|
|`indigo`|#4b0082|
|`ivory`|#fffff0|
|`khaki`|#f0e68c|
|`lavender`|#e6e6fa|
|`lavenderblush`|#fff0f5|
|`lawngreen`|#7cfc00|
|`lemonchiffon`|#fffacd|
|`lightblue`|#add8e6|
|`lightcoral`|#f08080|
|`lightcyan`|#e0ffff|
|`lightgoldenrodyellow`|#fafad2|
|`lightgray`|#d3d3d3|
|`lightgrey`|#d3d3d3|
|`lightgreen`|#90ee90|
|`lightpink`|#ffb6c1|
|`lightsalmon`|#ffa07a|
|`lightseagreen`|#20b2aa|
|`lightskyblue`|#87cefa|
|`lightslategray`|#778899|
|`lightsteelblue`|#b0c4de|
|`lightyellow`|#ffffe0|
|`lime`|#00ff00|
|`limegreen`|#32cd32|
|`linen`|#faf0e6|
|`magenta`|#ff00ff|
|`maroon`|#800000|
|`mediumaquamarine`|#66cdaa|
|`mediumblue`|#0000cd|
|`mediumorchid`|#ba55d3|
|`mediumpurple`|#9370db|
|`mediumseagreen`|#3cb371|
|`mediumslateblue`|#7b68ee|
|`mediumspringgreen`|#00fa9a|
|`mediumturquoise`|#48d1cc|
|`mediumvioletred`|#c71585|
|`midnightblue`|#191970|
|`mintcream`|#f5fffa|
|`mistyrose`|#ffe4e1|
|`moccasin`|#ffe4b5|
|`navajowhite`|#ffdead|
|`navy`|#000080|
|`oldlace`|#fdf5e6|
|`olive`|#808000|
|`olivedrab`|#6b8e23|
|`orange`|#ffa500|
|`orangered`|#ff4500|
|`orchid`|#da70d6|
|`palegoldenrod`|#eee8aa|
|`palegreen`|#98fb98|
|`paleturquoise`|#afeeee|
|`palevioletred`|#db7093|
|`papayawhip`|#ffefd5|
|`peachpuff`|#ffdab9|
|`peru`|#cd853f|
|`pink`|#ffc0cb|
|`plum`|#dda0dd|
|`powderblue`|#b0e0e6|
|`purple`|#800080|
|`red`|#ff0000|
|`rosybrown`|#bc8f8f|
|`royalblue`|#4169e1|
|`saddlebrown`|#8b4513|
|`salmon`|#fa8072|
|`sandybrown`|#f4a460|
|`seagreen`|#00ff00|
|`seashell`|#fff5ee|
|`sienna`|#a0522d|
|`silver`|#c0c0c0|
|`skyblue`|#87ceeb|
|`slateblue`|#6a5acd|
|`slategray`|#708090|
|`snow`|#fffafa|
|`springgreen`|#00ff7f|
|`steelblue`|#4682b4|
|`tan`|#d2b48c|
|`teal`|#008080|
|`thistle`|#d8bfd8|
|`tomato`|#ff6347|
|`turquoise`|#40e0d0|
|`violet`|#ee82ee|
|`wheat`|#f5deb3|
|`white`|#ffffff|
|`whitesmoke`|#f5f5f5|
|`yellow`|#ffff00|
|`yellowgreen`|#9acd32|
