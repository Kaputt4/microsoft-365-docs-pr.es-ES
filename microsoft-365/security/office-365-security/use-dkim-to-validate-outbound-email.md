---
title: Usar DKIM para el correo electrónico en su dominio personalizado en Office 365, 2048 bits, 1024 bits, pasos, cómo funciona, SPF, DMARC
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 'Resumen: Este artículo describe cómo usa DomainKeys Identified Mail (DKIM) con Office 365 para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde su dominio personalizado.'
ms.openlocfilehash: a570ec0c8002cc81a83da078705687b56ffe0bf1
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866432"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a>Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365

 **Resumen:** Este artículo describe cómo usa DomainKeys Identified Mail (DKIM) con Office 365 para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde su dominio personalizado.
  
Debería usar DKIM además de SPF y DMARC para ayudarle a evitar que los suplantadores de identidad envíen mensajes que parece que provienen de su dominio. DKIM le permite agregar una firma digital a los mensajes de correo electrónico salientes en el encabezado del mensaje. Puede sonar complicado, pero realmente no lo es. Cuando configura DKIM, autoriza su dominio para asociar, o firmar, su nombre a un mensaje de correo electrónico mediante la autenticación criptográfica. Los sistemas de correo electrónico que reciben correo electrónico desde el dominio pueden usar esta firma digital para ayudarles a determinar si el correo entrante que reciben es legítimo.
  
Básicamente, usa una clave privada para cifrar el encabezado del correo electrónico saliente del dominio. Publica una clave pública en los registros DNS del dominio que los servidores de recepción pueden usar para descodificar la firma. Usan la clave pública para comprobar que los mensajes proceden realmente de usted y no de alguien que está *suplantando la identidad* del dominio.
  
Office 365 configura automáticamente DKIM para sus dominios "onmicrosoft.com" iniciales. Eso significa que no es necesario hacer nada para configurar DKIM para ningún nombre de dominio inicial. (ex. litware.onmicrosoft.com). Para más información sobre los dominios, vea [Preguntas más frecuentes de dominios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).

También puede elegir no hacer nada acerca de DKIM para su dominio personalizado. Si usted no configura DKIM para su dominio personalizado, Office 365 crea un par de claves privadas y públicas, que permiten que DKIM firme y configure la directiva predeterminada de Office 365 para su dominio personalizado. Aunque esto suponga una cobertura suficiente para la mayoría de los clientes de Office 365, debería configurar manualmente DKIM para su dominio personalizado en las siguientes circunstancias:
  
- Tiene más de un dominio personalizado en Office 365

- También va a configurar DMARC (recomendado)

- Quiere tener el control sobre la clave privada

- Quiere personalizar los registros CNAME

- Quiere configurar claves de DKIM para los correos electrónicos que se originen en un dominio de terceros, por ejemplo, si usa un troyano de envío masivo de correo electrónico de terceros.

En este artículo:
  
- [Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada en Office 365](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [Actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [Pasos que necesita seguir para configurar manualmente DKIM en Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [Configurar DKIM para más de un dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [Deshabilitar la directiva de firmas DKIM para un dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [Comportamiento predeterminado para DKIM y Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [Pasos siguientes: Después de configurar DKIM para Office 365](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

> [!NOTE]
> Microsoft 365 es compatible con el usuario de 1024 bits ó DKIM de 2048 bits. Si utiliza 1024 y quiere configurar DKIM de 2048 bits, no se pierda los pasos para rotar la configuración de firma DKIM en este artículo. A finales de 2019, Microsoft será compatible con claves de 2048 bits de forma predeterminada para todos los clientes. 

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a>Cómo DKIM funciona mejor que solo SPF para evitar la suplantación de identidad malintencionada en Office 365
<a name="HowDKIMWorks"> </a>

SPF agrega información a un sobre del mensaje pero DKIM cifra realmente una firma dentro del encabezado del mensaje. Cuando reenvía un mensaje, el servidor de reenvío puede quitar partes de ese sobre del mensaje. Como la firma digital permanece en el mensaje de correo electrónico porque forma parte del encabezado del correo, DKIM funciona incluso cuando un mensaje se ha reenviado como se muestra en el siguiente ejemplo.
  
![Diagrama que muestra un mensaje reenviado que pasa por la autenticación DKIM, donde se produce un error en la comprobación de SPF.](../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
En este ejemplo, si solo había publicado un registro TXT de SPF en su dominio, el servidor de correo del destinatario podría haber marcado el correo electrónico como correo no deseado y generar un resultado de falso positivo. La adición de DKIM en este escenario reduce los informes de correo no deseado de falso positivo. Debido a que DKIM se basa en la criptografía de clave pública para autenticar y no solo en las direcciones IP, DKIM se considera una forma mucho más segura de autenticación que SPF. Se recomienda usar SPF y DKIM, así como DMARC, en la implementación.
  
Información esencial: DKIM usa una clave privada para insertar una firma cifrada en los encabezados del mensaje. El dominio de firma, o el dominio saliente, se inserta como el valor del campo **d=** en el encabezado. El dominio de comprobación, o dominio del destinatario, usa entonces el campo **=d** para buscar la clave pública desde DNS y autenticar el mensaje. Si el mensaje se comprueba, supera la comprobación DKIM. 

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>Actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits
<a name="1024to2048DKIM"> </a>

Ya que ambos valores de bits, 1024 y 2048, son compatibles con las claves DKIM, estas instrucciones le indicarán cómo actualizar la clave de 1024 bits a 2048. Los pasos que se muestran a continuación son dos casos de uso distintos, elija el que mejor se ajuste a su configuración.

1. Cuando **ya tiene configuradas las DKIM**, cambie el valor de los bits de la siguiente manera:
    1. [Conéctese con las cargas de trabajo de Office 365 a través de PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window). (El cmdlet viene de Exchange Online).
    1. Y luego ejecute el siguiente cmdlet:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}`

1. O para una **nueva implementación de DKIM**:
    1. [Conéctese con las cargas de trabajo de Office 365 a través de PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window). (Este es un cmdlet de Exchange Online).
    1. Ejecute el siguiente cmdlet:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True`

Manténgase conectado a Office 365 para *verificar* la configuración.

2. Ejecute el cmdlet:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `Get-DkimSigningConfig | fl`

> [!TIP]
>Esta nueva clave de 2048 bits tendrá efecto en el RotateOnDate y mientras tanto enviará los mensajes de correo electrónico con la clave de 1024 bits. Después de cuatro días, puede volver a probar con la clave de 2048 bits (es decir, cuando la rotación surta efecto al segundo selector). 

Si desea rotar hasta el segundo selector, las opciones son: a) dejar que el servicio de Office 365 rote el selector y actualice al valor de 2048 bits en los próximos 6 meses, o b) después de cuatro días y de confirmar que se está utilizando el valor de 2048 bits, rote manualmente la clave del segundo selector por usando el cmdlet apropiado de los que se enumeran arriba.

## <a name="steps-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a>Pasos que necesita seguir para configurar manualmente DKIM en Office 365
<a name="SetUpDKIMO365"> </a>

Para configurar DKIM, deberá completar estos pasos:
  
- [Publicar dos registros CNAME para su dominio personalizado en DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [Habilitar la firma DKIM para su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Publicar dos registros CNAME para su dominio personalizado en DNS
<a name="Publish2CNAME"> </a>

Para cada dominio para el que quiera agregar una firma DKIM en DNS, necesita publicar dos registros CNAME.

Ejecute los comandos siguientes:

```powershell
    New-DkimSigningConfig -DomainName <domain> -Enabled $false   
    Get-DkimSigningConfig -Identity <domain> | fl Selector1CNAME, Selector2CNAME
```

Cree registros CNAME a los que se hace referencia en los resultados de Get-DkimSigningConfig

```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
```

Los registros CNAME de sus DNS indicarán los registros DKIM TXT ya creados que existen en DNS en los servidores DNS de Microsoft para Office 365.
  
Office 365 realiza la rotación de claves automática mediante los dos registros que establezca. Si ha aprovisionado dominios personalizados adicionales además del dominio inicial de Office 365, debe publicar dos registros CNAME para cada dominio adicional. Por lo tanto, si tiene dos dominios, debe publicar dos registros CNAME adicionales, y así sucesivamente.
  
Use el formato siguiente para los registros CNAME.

> [!IMPORTANT]
> Si es uno de nuestros clientes de GCC High, calcularemos _domainGuid_ de forma diferente. En lugar de buscar el registro MX para su _initialDomain_ para calcular _domainGuid_, lo calculamos directamente desde el dominio personalizado. Por ejemplo, si su dominio personalizado es "contoso.com", su domainGuid se convierte en "contoso-com", los puntos se reemplazan por un guión. Por lo tanto, independientemente del registro MX al que señala su initialDomain, siempre se usará el método anterior para calcular el domainGuid que se usará en sus registros CNAME.

```text
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

Donde:
  
- Para Office 365, los selectores siempre serán "selector1" o "selector2".

- El _domainGUID_ es el mismo que el _domainGUID_ del registro MX personalizado para su dominio personalizado que aparece antes de mail.protection.outlook.com. Por ejemplo, en el siguiente registro MX del dominio contoso.com, el _domainGUID_ es contoso-com: 
    
    ```text
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- _initialDomain_ es el dominio que usó al registrarse en Office 365. Los dominios iniciales siempre terminan en onmicrosoft.com. Para obtener información sobre cómo determinar el dominio inicial, vea [Preguntas más frecuentes de dominios](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).

Por ejemplo, si tiene un dominio inicial de cohovineyardandwinery.onmicrosoft.com y dos dominios personalizados cohovineyard.com y cohowinery.com, necesitará configurar dos registros CNAME para cada dominio adicional, un total de cuatro registros CNAME.
  
```text
Host name:          selector1._domainkey
Points to address or value: selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
```

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a>Habilitar la firma DKIM para su dominio personalizado en Office 365
<a name="EnableDKIMinO365"> </a>

Una vez que haya publicado los registros CNAME en DNS, está preparado para habilitar la firma DKIM mediante Office 365. Puede hacerlo a través del Centro de administración de Microsoft 365 o mediante PowerShell.
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>Para habilitar la firma DKIM para su dominio personalizado a través del Centro de administración

1. [Inicie sesión en Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) con su cuenta profesional o educativa. 

2. Seleccione el icono del iniciador de aplicaciones en la esquina superior izquierda y elija **Administrador**.

3. En el panel de navegación inferior izquierdo, expanda **Administración** y elija **Exchange**.

4. Vaya a **Protección** \> **dkim**.

5. Seleccione el dominio para el que quiere habilitar DKIM y, después, en **Firmar los mensajes de este dominio con firmas DKIM**, elija **Habilitar**. Repita este paso para cada dominio personalizado.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>Para habilitar la firma DKIM para su dominio personalizado mediante PowerShell

1. [Conéctese al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Ejecute el siguiente comando:

    ```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
    ```

   Donde _domain_ es el nombre del dominio personalizado para el que quiere habilitar la firma DKIM. 

   Por ejemplo, para el dominio contoso.com:

    ```powershell
    Set-DkimSigningConfig -Identity contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a>Para confirmar que la firma DKIM está configurada correctamente en Office 365

Espere unos minutos antes de seguir estos pasos para confirmar que ha configurado correctamente DKIM. Esto proporciona tiempo para que la información DKIM acerca del dominio se reparta por toda la red.
  
- Envíe un mensaje desde una cuenta dentro de su dominio habilitado para DKIM en Office 365 a otra cuenta de correo electrónico como outlook.com o Hotmail.com.

- No use una cuenta de aol.com con fines de prueba. AOL puede omitir la comprobación DKIM si se supera la comprobación SPF. Esto anulará la prueba.

- Abra el mensaje y observe el encabezado. Las instrucciones para ver el encabezado del mensaje variarán según el cliente de mensajería. Para obtener instrucciones acerca de cómo ver los encabezados de los mensajes en Outlook, consulte [Ver encabezados de mensajes de correo electrónico](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).

  El mensaje con firma DKIM contendrá el nombre de host y el dominio que definió cuando publicó las entradas CNAME. El mensaje tendrá un aspecto similar al de este ejemplo:

  ```text
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- Busque el encabezado Authentication-Results. Aunque cada servicio de recepción usa un formato ligeramente diferente para estampar el correo entrante, el resultado debe incluir algo como **DKIM=pass** o **DKIM=OK**.

## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a>Configurar DKIM para más de un dominio personalizado en Office 365
<a name="DKIMMultiDomain"> </a>

Si en algún momento en el futuro decide agregar otro dominio personalizado y quiere habilitar DKIM para el dominio nuevo, debe completar los pasos de este artículo para cada dominio. En concreto, complete todos los pasos de [Lo que necesita hacer para configurar manualmente DKIM en Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a>Deshabilitar la directiva de firmas DKIM para un dominio personalizado en Office 365
<a name="DisableDKIMSigningPolicy"> </a>

Deshabilitar la directiva de firmas no deshabilita DKIM completamente. Después de un período de tiempo, Office 365 aplicará automáticamente la directiva de Office 365 predeterminada para el dominio. Para obtener más información, consulte [Comportamiento predeterminado para DKIM y Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Para deshabilitar la directiva de firmas DKIM mediante Windows PowerShell

1. [Conéctese al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Ejecute uno de los siguientes comandos para cada dominio para el que quiera deshabilitar la firma DKIM.
    
    ```powershell
    $p = Get-DkimSigningConfig -Identity <domain>
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

## <a name="default-behavior-for-dkim-and-office-365"></a>Comportamiento predeterminado para DKIM y Office 365
<a name="DefaultDKIMbehavior"> </a>

Si no habilita DKIM, Office 365 crea automáticamente una clave pública DKIM de 1024 bits para el dominio predeterminado y la clave privada asociada que se almacena internamente en nuestro centro de datos. De forma predeterminada, Office 365 usa una configuración de firmas predeterminada para los dominios que no tienen una directiva local. Esto significa que si no configura DKIM, Office 365 usará su política predeterminada y se creará la clave para habilitar DKIM para el dominio.
  
Además, si deshabilita la firma DKIM después de habilitarla, después de un período de tiempo, Office 365 aplicará automáticamente la directiva predeterminada de Office 365 para el dominio.
  
En el ejemplo siguiente, suponga que Office 365 ha habilitado DKIM para fabrikam.com, no el administrador del dominio. Esto significa que los CNAME necesarios no existen en DNS. Las firmas DKIM para el correo electrónico de este dominio tendrán un aspecto similar al siguiente:
  
```text
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

En este ejemplo, el nombre de host y el dominio contienen los valores a los que señalaría el registro CNAME si el administrador del dominio hubiera habilitado la firma DKIM para fabrikam.com. Finalmente, todos los mensajes enviados desde Office 365 contendrán una firma DKIM. Si habilita DKIM, el dominio será el mismo que el dominio que figura en la dirección del campo De:, en este caso, fabrikam.com. Si no lo hace, el dominio no se alineará y en su lugar se usará el dominio inicial de la organización. Para obtener información sobre cómo determinar el dominio inicial, vea [Preguntas más frecuentes de dominios](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado
<a name="SetUp3rdPartyspoof"> </a>

Algunos proveedores de servicio de correo electrónico masivo o proveedores de software como servicio, le permiten configurar claves DKIM para el correo electrónico que se origina de su servicio. Esto requiere la coordinación entre el usuario y el servicio de terceros para configurar los registros DNS necesarios. No existen dos organizaciones que lo hagan exactamente de la misma manera. En su lugar, el proceso depende completamente de la organización.
  
Un mensaje de ejemplo que muestra un DKIM configurado correctamente para contoso.com y bulkemailprovider.com puede tener el aspecto siguiente:
  
```text
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

En este ejemplo, para conseguir este resultado:
  
1. El proveedor de correo electrónico masivo le ha proporcionado una clave DKIM pública a Contoso.

2. Contoso ha publicado la clave DKIM en su registro DNS.

3. Al enviar el correo electrónico, el proveedor de correo electrónico masivo ha firmado la clave con la clave privada correspondiente. Al hacer esto, el proveedor de correo electrónico masivo ha adjuntado la firma DKIM al encabezado del mensaje.

4. Los sistemas de correo electrónico de recepción realizan una comprobación DKIM mediante la autenticación del valor d=\<dominio\> de la firma DKIM contra el dominio del campo De: (5322.From) dirección del mensaje. En este ejemplo, los valores coinciden:

    sender@**contoso.com**

    d=**contoso.com**

## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a>Pasos siguientes: una vez configurado DKIM para Office 365
<a name="DKIMNextSteps"> </a>

Aunque DKIM está diseñado para ayudar a evitar la suplantación de identidad, DKIM funciona mejor con SPF y DMARC. Cuando haya configurado DKIM, si todavía no ha configurado SPF, debería hacerlo. Para obtener una introducción rápida a SPF y configurarlo rápidamente, vea [Configurar SPF en Office 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para comprender en detalle cómo Office 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md). A continuación, consulte [Usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md). Los [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md) incluyen la sintaxis y los campos de encabezado que usa Office 365 para efectuar las comprobaciones de DKIM.
