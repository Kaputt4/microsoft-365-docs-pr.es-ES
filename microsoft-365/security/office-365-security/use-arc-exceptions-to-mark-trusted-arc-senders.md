---
title: Usar remitentes de ARC de confianza para dispositivos y servicios legítimos entre el remitente y el receptor
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: high
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: La cadena de recepción autenticada (ARC) es la autenticación del correo electrónico que intenta preservar los resultados de la autenticación a través de los dispositivos y cualquier flujo de correo indirecto que se interponga entre el remitente y el destinatario. Aquí se muestra cómo realizar excepciones para los remitentes ARC de confianza.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6b3057350f8b1a652a08da8c878a47e191af04d0
ms.sourcegitcommit: 38a18b0195d99222c2c6da0c80838d24b5f66b97
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2022
ms.locfileid: "66998153"
---
# <a name="make-a-list-of-trusted-arc-senders-to-trust-legitimate-indirect-mailflows"></a>Crear una lista de remitentes ARC de confianza para confiar en los flujos de correo indirectos *legítimos* 

**Se aplica a**

- Exchange Online Protection
- Plan 1 y Plan 2 de Microsoft Defender para Office 365
- Microsoft 365 Defender

Los mecanismos de autenticación de los correos electrónicos como [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md) y [DMARC](use-dmarc-to-validate-email.md) se usan para comprobar los remitentes de los correos electrónicos para la *seguridad* de los destinatarios de correos electrónicos, pero algunos servicios legítimos pueden realizar cambios en el correo electrónico entre el remitente y el destinatario. **En Microsoft 365 Defender, ARC permite reducir los errores de entrega de SPF, DKIM y DMARC que se producen debido a flujos de correo indirectos *legítimos*.**

## <a name="authenticated-received-chain-arc-in-microsoft-365-defender-for-office"></a>Cadena de recepción autenticada (ARC) en Microsoft 365 Defender para Office

Los servicios que modifican el contenido durante el transporte del mensaje antes de la entrega a la organización pueden invalidar la firma de correo electrónico DKIM y afectar a la autenticación del mensaje. Cuando estos servicios intermedios, realizan tales acciones, pueden utilizar ARC para proporcionar detalles de la autenticación original antes de que se produzcan las modificaciones, que su organización puede entonces confiar para ayudar con la autenticación del mensaje.  

**Los sealers ARC de confianza permiten a los administradores agregar una lista de intermediarios de *confianza* en el portal de Microsoft 365 Defender.** Los sealers ARC de confianza permiten a Microsoft respetar las firmas ARC de estos intermediarios de confianza, lo que impide que estos mensajes legítimos produzcan errores en la cadena de autenticación.

> [!NOTE]
> ***Los sealers ARC de confianza son una lista creada por el administrador de dominios intermedios que han implementado el sealing ARC.*** Cuando un correo electrónico se enruta a Office 365 a través del intermediario ARC de confianza del inquilino de Office 365, Microsoft valida la firma ARC y, en función de los resultados de ARC, puede respetar los detalles de autenticación proporcionados.

## <a name="when-to-use-trusted-arc-sealers"></a>¿Cuándo usar sealers ARC de confianza?

Solo se necesita una lista de sealers ARC de confianza en los que los intermediarios formen parte del flujo de correo electrónico de una organización y:

1. Puede modificar el encabezado o el contenido del correo electrónico.
2. Puede provocar un error de autenticación por otros motivos (por ejemplo, mediante la eliminación de datos adjuntos).
 
Al agregar un seler ARC de confianza, Office 365 validará y confiará en los resultados de autenticación que proporciona el sealer al entregar el correo a su espacio empresarial en Office 365.

**Los administradores solo deben agregar *servicios legítimos* como sealers ARC de confianza.** Agregar solo los servicios que la organización usa y conoce expresamente ayudará a que los mensajes que deben pasar primero por un servicio superen las comprobaciones de autenticación de correo electrónico y evitará que los mensajes legítimos se desplacen al *correo no deseado* debido a errores de autenticación.

## <a name="steps-to-add-a-trusted-arc-sealer-to-microsoft-365-defender"></a>Pasos para agregar un sealer ARC de confianza a Microsoft 365 Defender

Los sealers ARC de confianza en el portal Microsoft 365 Defender muestran todos los sealers ARC conocidos y agregados al inquilino.

**Para agregar un nuevo sealer ARC de confianza en el portal de administración:**

1. Vaya a la página [de configuración de autenticación de correo electrónico](https://security.microsoft.com/authentication?viewid=ARC).

2. Si es la primera vez que agrega un sealer ARC de confianza, haga clic en el botón Agregar.
3. Agregue sealers ARC de confianza en el cuadro de texto que se muestra.
    1. Tenga en cuenta que va a agregar los dominios (ejemplo fabrikam.com).
    1. El nombre de dominio que escriba aquí *debe* coincidir con el dominio que se muestra en la etiqueta "d" del dominio en los encabezados ARC-Seal y ARC-Message-Signature (en los encabezados de correo electrónico del mensaje).
    1. Puede verlos en las propiedades del mensaje en Outlook.

## <a name="steps-to-validate-your-trusted-arc-sealer"></a>Pasos para validar su sealer ARC de confianza

Si hay un seal ARC de un tercero antes de que el mensaje llegue a Microsoft 365 Defender, **compruebe los encabezados una vez recibido el correo electrónico y vea los encabezados ARC más recientes**.

En el último ***encabezado *ARC-Authentication-Results** _, compruebe si la validación ARC aparece como _*pass**.

Un encabezado ARC que enumera una "oda" de 1 indica que se ha *comprobado*, que el sealer ARC anterior es de *confianza* y que se puede usar el *resultado del paso* anterior para invalidar el error DMARC actual.

**Un encabezado ARC de paso que muestra oda=1**

Consulte los métodos de autenticación de correo electrónico al final de este bloque de encabezado para obtener el resultado de oda.

``
ARC-Authentication-Results: i=2; mx.microsoft.com 1; spf=pass (sender ip is
40.107.65.78) smtp.rcpttodomain=microsoft.com
smtp.mailfrom=sampledoamin.onmicrosoft.com; dmarc=bestguesspass action=none
header.from=sampledoamin.onmicrosoft.com; dkim=none (message not signed);
arc=pass (0 oda=1 ltdi=1
spf=[1,1,smtp.mailfrom=sampledoamin.onmicrosoft.com]
dkim=[1,1,header.d=sampledoamin.onmicrosoft.com]
dmarc=[1,1,header.from=sampledoamin.onmicrosoft.com])
``

Para comprobar si el resultado ARC se usó para invalidar un error DMARC, busque el resultado *compauth* y un *motivo de código (130)* en el encabezado.

Consulte la última entrada de este bloque de encabezado para encontrar *compauth* y el *motivo*.

``
Authentication-Results: spf=fail (sender IP is 51.163.158.241)
smtp.mailfrom=contoso.com; dkim=fail (body hash did not verify)
header.d=contoso.com;dmarc=fail action=none
header.from=contoso.com;compauth=pass reason=130
``

## <a name="powershell-steps-to-add-or-remove-a-trusted-arc-sealer"></a>Pasos de PowerShell para agregar o quitar un sealer ARC de confianza

**Los administradores también pueden configurar las configuraciones ARC con Exchange Online PowerShell.**

1. Conectarse a Exchange Online mediante PowerShell.
2. Connect-ExchangeOnline.
3. Para agregar o actualizar un dominio en un sealer ARC de confianza:
</br>
``
Set-ArcConfig -Identity default -ArcTrustedSealers {a list of arc signing domains split by comma}
``
</br>o</br>
``
Set-ArcConfig -Identity {tenant name/tenanid}\default -ArcTrustedSealers {a list of arc signing domains split by comma}
``
</br>Debe proporcionar el parámetro de identidad *-Identity* predeterminado al ejecutar *Set-ArcConfig*. Los sealers de confianza deben coincidir con el valor de la etiqueta "d" en el *encabezado ARC-Seal*.

4. Vea los sealers ARC de confianza:
</br>
``
Get-ArcConfig
`` o ``
Get-ArcConfig - Organization {tenant name}
``

## <a name="trusted-arc-sealer-mailflow-graphics"></a>Gráficos de flujo de correo del sealer ARC de confianza

Estos diagramas contrastan las operaciones de flujo de correo con y sin un sealer ARC de confianza, cuando se usa cualquiera de las autenticaciones de correo electrónico SPF, DKIM y DMARC. En ambos gráficos, hay servicios legítimos usados por la empresa que deben intervenir en el flujo de correo, a veces infringiendo las normas de autenticación de correo electrónico cambiando las direcciones IP de envío y escribiendo en el encabezado del correo electrónico. **En el primer caso, el tráfico de flujo de correo indirecto muestra el resultado *antes* de que los administradores agreguen un sealer ARC de confianza.**

:::image type="content" source="../../media/m365d-indirect-traffic-flow-without-trusted-arc-sealer.PNG" alt-text="En este gráfico, Contoso publica SPF, DKIM y DMARC como parte de la seguridad estándar del correo electrónico. Un remitente que usa SPF envía el correo desde el interior de contoso.com a fabrikam.com, y este correo pasa a través de un servicio de terceros que Contoso ha contratado, y ese servicio modifica la dirección IP de envío en el encabezado de correo electrónico. El correo produce un error SPF debido a la dirección IP modificada y DKIM, porque el contenido se ha modificado en un tercero, durante la comprobación DNS en EOP. DMARC produce un error SPF y DKIM. El mensaje se envía a Correo no deseado, Cuarentena o Rechazado.":::

Aquí verá la misma organización **después de aprovechar la capacidad de crear un sealer ARC de confianza.**

:::image type="content" source="../../media/m365d-indirect-traffic-flow-with-trusted-arc-sealer.PNG" alt-text="En el segundo gráfico, la empresa Contoso había creado una lista de sealers ARC de confianza. El mismo usuario envía un segundo correo desde contoso.com a fabrikam.com. El servicio de terceros contratado por Contoso modifica la dirección IP del remitente en el encabezado del correo. Pero esta vez el servicio ha implementado el sealing ARC y, dado que el administrador de inquilinos ya ha agregado el dominio del tercero a los sealers ARC de confianza, se acepta la modificación. Se produce un error de SPF para la nueva dirección IP. DKIM produce un error debido a la modificación del contenido. DMARC produce un error debido a los errores anteriores. Pero ARC reconoce las modificaciones, emite un pase y acepta los cambios. La suplantación de identidad también recibe un pase. El mensaje se envía a la bandeja de entrada.":::

## <a name="next-steps-after-you-set-up-arc-for-microsoft-365-defender-for-office"></a>Próximos pasos: después de configurar ARC para Microsoft 365 Defender para Office

Después de la configuración, compruebe los encabezados ARC con el [Analizador de encabezados de mensaje](/connectivity-analyzer/message-header-analyzer).

Revise los pasos de configuración [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md) y [DMARC](use-dmarc-to-validate-email.md).
