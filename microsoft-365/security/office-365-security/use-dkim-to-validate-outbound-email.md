---
title: Cómo usar DKIM para el correo electrónico en su dominio personalizado
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
audience: ITPro
ms.topic: article
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Más información sobre cómo usar DomainKeys Identified Mail (DKIM) con Microsoft 365 para asegurarse de que los mensajes que se envían desde su dominio personalizado sean de confianza para los sistemas de correo electrónico de destino.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b5e852e26d1fc336a52255ea8fc7a90ab384c64c
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53544486"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a>Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 Este artículo muestra los pasos para usar DomainKeys Identified Mail (DKIM) con Microsoft 365 para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde su dominio personalizado.

En este artículo:

- [Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada](#how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing)
- [Pasos para actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits](#steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys)
- [Pasos para configurar manualmente DKIM](#steps-to-manually-set-up-dkim)
- [Pasos para configurar DKIM para más de un dominio personalizado](#to-configure-dkim-for-more-than-one-custom-domain)
- [Deshabilitar la directiva de firmas DKIM para un dominio personalizado](#disabling-the-dkim-signing-policy-for-a-custom-domain)
- [Comportamiento predeterminado para DKIM y Microsoft 365](#default-behavior-for-dkim-and-microsoft-365)
- [Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado](#set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain)
- [Pasos siguientes: una vez configurado DKIM para Microsoft 365](#next-steps-after-you-set-up-dkim-for-microsoft-365)

> [!NOTE]
> Microsoft 365 configura automáticamente DKIM para sus dominios "onmicrosoft.com" iniciales. Lo que significa que no es necesario realizar ninguna acción para configurar DKIM para un nombre de dominio inicial (por ejemplo, litware.onmicrosoft.com). Para más información sobre los dominios, vea [Preguntas más frecuentes de dominios](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

DKIM es uno de los tres métodos de autenticación (SPF, KIM y DMARC) que ayudan a evitar que los atacantes envíen mensajes que parecen procedentes de su dominio.

DKIM le permite agregar una firma digital a los mensajes de correo electrónico salientes en el encabezado del mensaje. Suena complicado, pero realmente no lo es. Cuando configura DKIM, autoriza que su dominio pueda asociar su nombre (o firmar) a un mensaje de correo electrónico mediante la autenticación criptográfica. Los sistemas de correo electrónico que reciben correo electrónico desde el dominio pueden usar esta firma digital para ayudar a determinar si el correo entrante que reciben es legítimo.

Básicamente, una clave privada cifra el encabezado en un correo electrónico saliente del dominio. La clave pública se publica en los registros DNS del dominio, y los servidores de recepción pueden usar esa clave para descodificar la firma. La verificación de DKIM ayuda a los servidores de recepción a confirmar que el correo realmente procede de su dominio y no se trata de alguien que está *suplantando* su dominio.

> [!TIP]
>También puede elegir no hacer nada relacionado con DKIM para su dominio personalizado. Si no configura DKIM para su dominio personalizado, Microsoft 365 crea un par de claves privadas y públicas que permiten que DKIM firme y configure la directiva predeterminada de Microsoft 365 para su dominio personalizado.

 El DKIM integrado de Microsoft 365 es una cobertura suficiente para la mayoría de los clientes. Sin embargo, debería configurar manualmente DKIM para su dominio personalizado en las siguientes circunstancias:

- Tiene más de un dominio personalizado en Microsoft 365
- También va a configurar DMARC (**recomendado**)
- Quiere tener el control sobre la clave privada
- Quiere personalizar los registros CNAME
- Quiere configurar claves de DKIM para los correos electrónicos que se originen en un dominio de terceros, por ejemplo, si usa un troyano de envío masivo de correo electrónico de terceros.

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a>Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada
<a name="HowDKIMWorks"> </a>

SPF agrega información a un sobre del mensaje pero DKIM *cifra* una firma dentro del encabezado del mensaje. Cuando reenvía un mensaje, el servidor de reenvío puede quitar partes de ese sobre del mensaje. Como la firma digital permanece en el mensaje de correo electrónico porque forma parte del encabezado del correo, DKIM funciona incluso cuando un mensaje se ha reenviado como se muestra en el siguiente ejemplo.

![Diagrama que muestra un mensaje reenviado que pasa por la autenticación DKIM, donde se produce un error en la comprobación de SPF.](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

En este ejemplo, si solo había publicado un registro TXT de SPF en su dominio, el servidor de correo del destinatario podría haber marcado el correo electrónico como correo no deseado y generar un resultado de falso positivo. **La adición de DKIM en este escenario reduce los *informes de correo no deseado* de falso positivo**. Debido a que DKIM se basa en la criptografía de clave pública para autenticar y no solo en las direcciones IP, DKIM se considera una forma mucho más segura de autenticación que SPF. Se recomienda usar SPF y DKIM, así como DMARC, en la implementación.

> [!TIP]
> DKIM usa una clave privada para insertar una firma cifrada en los encabezados del mensaje. El dominio de firma, o el dominio saliente, se inserta como el valor del campo **d=** en el encabezado. El dominio de comprobación, o dominio del destinatario, usa entonces el campo **=d** para buscar la clave pública desde DNS y autenticar el mensaje. Si el mensaje se comprueba, supera la comprobación DKIM.


## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>Pasos para actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits
<a name="1024to2048DKIM"> </a>

> [!NOTE]
> Microsoft 365 configura automáticamente DKIM para los dominios *"onmicrosoft.com"*. No es necesario seguir ningún paso para usar DKIM para los nombres de dominio iniciales (como litware.*onmicrosoft.com*). Para más información sobre los dominios, vea [Preguntas más frecuentes de dominios](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Ya que ambos valores de bits, 1024 y 2048, son compatibles con las claves DKIM, estas instrucciones le indicarán cómo actualizar la clave de 1024 bits a 2048 en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Los pasos que se muestran a continuación son dos casos de uso distintos, elija el que mejor se ajuste a su configuración.

- Cuando **ya tenga DKIM configurado**, cambie el valor de los bits ejecutando el siguiente comando:

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
  ```

  **o bien**

- Para una **implementación nueva de DKIM**, ejecute el siguiente comando:

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

Permanezca conectado a Exchange Online PowerShell para *comprobar* la configuración ejecutando el comando siguiente:

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> Esta nueva clave de 2048 bits tendrá efecto en el RotateOnDate y mientras tanto enviará los mensajes de correo electrónico con la clave de 1024 bits. Después de cuatro días, puede volver a probar con la clave de 2048 bits (es decir, cuando la rotación surta efecto al segundo selector).

Si desea girar al segundo selector, después de cuatro días y confirmando que el valor de 2048 bits está en uso, gire manualmente la segunda clave de selector mediante el cmdlet adecuado indicado anteriormente.

Para obtener información detallada sobre la sintaxis y los parámetros, vea los siguientes artículos: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig) y [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).

## <a name="steps-to-manually-set-up-dkim"></a>Pasos que necesita seguir para configurar manualmente DKIM
<a name="SetUpDKIMO365"> </a>

Para configurar DKIM, deberá completar estos pasos:

- [Publicar dos registros CNAME para su dominio personalizado en DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
- [Habilitar la firma DKIM para su dominio personalizado](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Publicar dos registros CNAME para su dominio personalizado en DNS
<a name="Publish2CNAME"> </a>

Para cada dominio para el que quiera agregar una firma DKIM en DNS, necesita publicar dos registros CNAME.

> [!NOTE]
> Si no ha leído el artículo completo, es posible que se haya perdido esta información de conexión de PowerShell para ahorrar tiempo: [Conectarse a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Ejecute los siguientes comandos de Exchange Online PowerShell para crear los registros del selector:

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

Si ha aprovisionado dominios personalizados adicionales además del dominio inicial de Microsoft 365, debe publicar dos registros CNAME para cada dominio adicional. Por lo tanto, si tiene dos dominios, debe publicar dos registros CNAME adicionales, y así sucesivamente.

Use el formato siguiente para los registros CNAME.

> [!IMPORTANT]
> Si es uno de nuestros clientes de GCC High, calcularemos _domainGuid_ de forma diferente. En lugar de buscar el registro MX para su _initialDomain_ para calcular _domainGuid_, lo calculamos directamente desde el dominio personalizado. Por ejemplo, si su dominio personalizado es "contoso.com", su domainGuid se convierte en "contoso-com", los puntos se reemplazan por un guión. Por lo tanto, independientemente del registro MX al que señale su initialDomain, siempre se usará el método anterior para calcular el domainGuid que se usará en sus registros CNAME.

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

Donde:

- Para Microsoft 365, los selectores siempre serán "selector1" o "selector2".
- _domainGUID_ es el mismo que el _domainGUID_ en el registro MX personalizado para su dominio personalizado que aparece antes de mail.protection.outlook.com. Por ejemplo, en el siguiente registro MX del dominio contoso.com, el _domainGUID_ es contoso-com:

  > contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com

- _initialDomain_ es el dominio que usó al registrarse en Microsoft 365. Los dominios iniciales siempre terminan en onmicrosoft.com. Para obtener información sobre cómo determinar el dominio inicial, vea [Preguntas más frecuentes de dominios](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Por ejemplo, si tiene un dominio inicial de cohovineyardandwinery.onmicrosoft.com y dos dominios personalizados cohovineyard.com y cohowinery.com, necesitará configurar dos registros CNAME para cada dominio adicional, un total de cuatro registros CNAME.

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> Es importante crear el segundo registro, pero solo uno de los selectores puede estar disponible en el momento de la creación. En esencia, el segundo selector podría apuntar a una dirección que aún no ha sido creada. Aun así, recomendamos crear el segundo registro CNAME, ya que la rotación de las teclas será perfecta.

### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a>Pasos para habilitar la firma DKIM para su dominio personalizado
<a name="EnableDKIMinO365"> </a>

Una vez que haya publicado los registros CNAME en DNS, está preparado para habilitar la firma DKIM mediante Microsoft 365. Puede hacerlo a través del Centro de administración de Microsoft 365 o mediante PowerShell.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-in-the-microsoft-365-defender-portal"></a>Para habilitar la firma DKIM para el dominio personalizado en el portal de Microsoft 365 Defender

1. Abra el portal de Microsoft 365 Defender [con su cuenta profesional o educativa](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **página de Directivas de amenazas** \> sección de **Reglas** \> **DKIM**. O bien, para ir directamente a la página de DKIM, use <https://security.microsoft.com/dkimv2>.

3. En la página **DKIM**, haga clic en el nombre para seleccionar el dominio.

4. En el control flotante de detalles que aparece, cambie el ajuste **Firmar mensajes para este dominio con firmas DKIM** a **Habilitado** (![activar](../../media/scc-toggle-on.png))

   Cuando haya terminado, haga clic en **Girar claves DKIM**.

5. Repita estos pasos para cada dominio personalizado.

6. Si va a configurar DKIM por primera vez y ve el error "No hay claves DKIM guardadas para este dominio", tendrá que usar Windows PowerShell para habilitar la firma DKIM, como se explica en el paso siguiente.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>Para habilitar la firma DKIM para su dominio personalizado mediante PowerShell

> [!IMPORTANT]
> :::image type="content" source="../../media/dkim.png" alt-text="El error &quot;No hay claves DKIM guardadas para este dominio&quot;.":::
> Si va a configurar DKIM por primera vez y ve el error "No hay claves DKIM guardadas para este dominio", complete el comando del paso 2 siguiente (por ejemplo, `Set-DkimSigningConfig -Identity contoso.com -Enabled $true`) para ver la clave.

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Utilice la siguiente sintaxis:

   ```powershell
   Set-DkimSigningConfig -Identity <Domain> -Enabled $true
   ```

   \<Domain\> es el nombre del dominio personalizado para el que quiere habilitar la firma DKIM.

   En este ejemplo se habilita la firma DKIM para el dominio contoso.com:

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a>Para confirmar que la firma DKIM está configurada correctamente en Microsoft 365

Espere unos minutos antes de seguir estos pasos para confirmar que ha configurado correctamente DKIM. Esto proporciona tiempo para que la información DKIM acerca del dominio se reparta por toda la red.

- Envíe un mensaje desde una cuenta dentro de su dominio habilitado para DKIM en Microsoft 365 a otra cuenta de correo electrónico como outlook.com o Hotmail.com.
- No use una cuenta de aol.com con fines de prueba. AOL puede omitir la comprobación DKIM si se supera la comprobación SPF. Esto anulará la prueba.
- Abra el mensaje y observe el encabezado. Las instrucciones para ver el encabezado del mensaje variarán según el cliente de mensajería. Para obtener instrucciones acerca de cómo ver los encabezados de los mensajes en Outlook, consulte [Ver los encabezados de los mensajes de Internet en Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

  El mensaje con firma DKIM contendrá el nombre de host y el dominio que definió cuando publicó las entradas CNAME. El mensaje tendrá un aspecto similar al de este ejemplo:

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- Busque el encabezado Authentication-Results. Aunque cada servicio de recepción usa un formato ligeramente diferente para estampar el correo entrante, el resultado debe incluir algo como **DKIM=pass** o **DKIM=OK**.

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a>Configuración de DKIM para más de un dominio personalizado
<a name="DKIMMultiDomain"> </a>

Si en algún momento en el futuro decide agregar otro dominio personalizado y quiere habilitar DKIM para el dominio nuevo, debe completar los pasos de este artículo para cada dominio. En concreto, complete todos los pasos de [Lo que necesita hacer para configurar manualmente DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a>Deshabilitación de la directiva de firmas DKIM para un dominio personalizado
<a name="DisableDKIMSigningPolicy"> </a>

Deshabilitar la directiva de firmas no deshabilita DKIM completamente. Después de un período de tiempo, Microsoft 365 aplicará automáticamente la directiva predeterminada para el dominio, si la directiva predeterminada sigue en estado habilitado. Si desea deshabilitar completamente DKIM, debe deshabilitar DKIM en los dominios personalizados y predeterminados. Para más información sobre esta firma, consulte [Comportamiento predeterminado para DKIM y Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Para deshabilitar la directiva de firmas DKIM mediante Windows PowerShell

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute uno de los siguientes comandos para cada dominio para el que quiera deshabilitar la firma DKIM.

   ```powershell
   $p = Get-DkimSigningConfig -Identity <Domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   Por ejemplo:

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   O bien

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   Donde _number_ es el índice de la directiva. Por ejemplo:

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a>Comportamiento predeterminado para DKIM y Microsoft 365
<a name="DefaultDKIMbehavior"> </a>

Si no habilita DKIM, Microsoft 365 crea automáticamente una clave pública DKIM de 1024 bits para su dirección de enrutamiento de correo electrónico en línea de Microsoft (MOERA) / dominio inicial y la clave privada asociada que almacenamos internamente en nuestro centro de datos. De forma predeterminada, Microsoft 365 usa una configuración de firma predeterminada para los dominios que no tienen una política establecida. Esto significa que si no configura DKIM usted mismo, Microsoft 365 usará su política predeterminada y las claves que crea para habilitar DKIM para su dominio.

Además, si deshabilita la firma DKIM en el dominio personalizado después de habilitarlo, después de un período de tiempo, Microsoft 365 aplicará automáticamente la directiva de dominio inicial o MOERA para el dominio personalizado.

En el ejemplo siguiente, suponga que Microsoft 365 ha habilitado DKIM para fabrikam.com, no el administrador del dominio. Esto significa que los CNAME necesarios no existen en DNS. Las firmas DKIM para el correo electrónico de este dominio tendrán un aspecto similar al siguiente:

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

En este ejemplo, el nombre de host y el dominio contienen los valores a los que señalaría el registro CNAME si el administrador del dominio hubiera habilitado la firma DKIM para fabrikam.com. Finalmente, cada mensaje enviado desde Microsoft 365 contendrá una firma DKIM. Si habilita DKIM, el dominio será el mismo que el dominio de la dirección en el campo De:, en este caso, fabrikam.com. Si no lo hace, el dominio no se alineará y en su lugar se usará el dominio inicial de la organización. Para obtener información sobre cómo determinar el dominio inicial, vea [Preguntas más frecuentes de dominios](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado
<a name="SetUp3rdPartyspoof"> </a>

Algunos proveedores de servicio de correo electrónico masivo o proveedores de software como servicio le permiten configurar claves DKIM para el correo electrónico que se origina de su servicio. Esto requiere la coordinación entre el usuario y el servicio de terceros para configurar los registros DNS necesarios. Algunos servidores de terceros pueden tener sus propios registros CNAME con diferentes selectores. No existen dos organizaciones que lo hagan exactamente de la misma manera. En su lugar, el proceso depende completamente de la organización.

Un mensaje de ejemplo que muestra un DKIM configurado correctamente para contoso.com y bulkemailprovider.com puede tener el aspecto siguiente:

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

En este ejemplo, para conseguir este resultado:

1. El proveedor de correo electrónico masivo le ha proporcionado una clave DKIM pública a Contoso.

2. Contoso ha publicado la clave DKIM en su registro DNS.

3. Al enviar el correo electrónico, el proveedor de correo electrónico masivo ha firmado la clave con la clave privada correspondiente. Al hacer esto, el proveedor de correo electrónico masivo ha adjuntado la firma DKIM al encabezado del mensaje.

4. Los sistemas de correo electrónico de recepción realizan una comprobación DKIM mediante la autenticación del valor d=\<domain\> comparado con el dominio en el campo De: (5322.From) de la dirección del mensaje. En este ejemplo, los valores coinciden:

   > sender@**contoso.com**

   > d=**contoso.com**

## <a name="identify-domains-that-do-not-send-email"></a>Identificar dominios que no envían correos electrónicos

Las organizaciones deben indicar explícitamente si un dominio no envía correos electrónicos especificando `v=DKIM1; p=` en el registro DKIM de estos dominios. Esto aconseja rechazar la recepción de servidores de correo electrónico que no tengan claves públicas válidas para el dominio y cualquier correo electrónico que declare ser de ese dominio. Debe hacerlo para cada dominio y subdominio mediante un carácter comodín DKIM.

Por ejemplo, el registro DKIM tendría el siguiente aspecto:

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a>Pasos siguientes: una vez configurado DKIM para Microsoft 365
<a name="DKIMNextSteps"> </a>

Aunque DKIM está diseñado para ayudar a evitar la suplantación de identidad, DKIM funciona mejor con SPF y DMARC. Cuando haya configurado DKIM, si todavía no ha configurado SPF, debería hacerlo. Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [Configuración de SPF en Microsoft 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para comprender en detalle cómo Microsoft 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md) (Cómo Microsoft 365 usa el marco de directivas permanente [SPF] para evitar la suplantación de identidad). Después, consulte [Uso de DMARC para validar el correo electrónico](use-dmarc-to-validate-email.md). Los [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md) incluyen la sintaxis y los campos de encabezado que usa Microsoft 365 para efectuar comprobaciones de DKIM.

## <a name="more-information"></a>Más información

Rotación de clave mediante PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)
