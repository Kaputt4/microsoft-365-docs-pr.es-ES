---
title: Información de la inteligencia contra la suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la información de inteligencia sobre suplantación de identidad en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c147396ff47f924d7dd4b2ebd3a0cac106de94b2
ms.sourcegitcommit: 58ec09f1fd66af9717dc2743585d06d358ec7360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2022
ms.locfileid: "65144737"
---
# <a name="spoof-intelligence-insight-in-eop"></a>Información de inteligencia sobre suplantación de identidad en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones de correo en organizaciones Exchange Online o independientes de Exchange Online Protection (EOP) sin Exchange Online buzones, los mensajes de correo electrónico entrantes se protegen automáticamente contra la suplantación de identidad. EOP usa **inteligencia de suplantación de identidad** como parte de la defensa general de su organización contra la suplantación de identidad (phishing). Para obtener más información, vea [Protección contra la suplantación de identidad en EOP](anti-spoofing-protection.md).

Cuando un remitente suplanta una dirección de correo electrónico, parece ser un usuario de uno de los dominios de la organización o un usuario de un dominio externo que envía correo electrónico a su organización. Los atacantes que suplantan a los remitentes para enviar correo no deseado o correo electrónico de suplantación de identidad deben bloquearse. Pero hay escenarios en los que los remitentes legítimos son suplantados. Por ejemplo:

- Escenarios legítimos para suplantar dominios internos:
  - Los remitentes de terceros usan su dominio para enviar correo masivo a sus propios empleados para sondeos de empresa.
  - Una empresa externa genera y envía publicidad o actualizaciones de productos en su nombre.
  - Un asistente debe enviar periódicamente correo electrónico a otra persona de la organización.
  - Una aplicación interna envía notificaciones por correo electrónico.

- Escenarios legítimos para suplantar dominios externos:
  - El remitente está en una lista de correo (también conocida como lista de discusión) y la lista de distribución retransmite el correo electrónico del remitente original a todos los participantes de la lista de correo.
  - Una empresa externa envía un correo electrónico en nombre de otra empresa (por ejemplo, un informe automatizado o una empresa de software como servicio).

Puede usar la **información de inteligencia sobre suplantación** de identidad en el portal de Microsoft 365 Defender para identificar rápidamente a los remitentes suplantados que le envían legítimamente correo electrónico no autenticado (mensajes de dominios que no pasan comprobaciones de SPF, DKIM o DMARC) y permitir manualmente esos remitentes.

Al permitir que los remitentes conocidos envíen mensajes suplantados desde ubicaciones conocidas, puede reducir los falsos positivos (un buen correo electrónico marcado como incorrecto). Al supervisar los remitentes suplantados permitidos, proporciona una capa de seguridad adicional para evitar que lleguen mensajes no seguros a su organización.

Del mismo modo, puede revisar los remitentes suplantados permitidos por la inteligencia de suplantación de identidad y bloquear manualmente a esos remitentes de la información de inteligencia de suplantación de identidad.

En el resto de este artículo se explica cómo usar la información de inteligencia sobre suplantación de identidad en el portal de Microsoft 365 Defender y en PowerShell (Exchange Online PowerShell para organizaciones Microsoft 365 con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin Exchange Online buzones).

> [!NOTE]
>
> - En la información de inteligencia sobre suplantación de identidad solo aparecen los remitentes suplantados detectados por la inteligencia suplantada. Al invalidar el veredicto de permitir o bloquear en la información, el remitente suplantado se convierte en una entrada manual de permitir o bloquear que aparece solo en la pestaña **Suplantación** de identidad en la lista de permitidos o bloqueados de inquilinos. También puede crear manualmente entradas de permitir o bloquear para remitentes suplantados antes de que se detecten mediante inteligencia de suplantación de identidad. Para obtener más información, consulte [Administrar la lista de permitidos y bloqueados del espacio empresarial en EOP](tenant-allow-block-list.md).
>
> - La información de inteligencia de suplantación y la pestaña **Suplantación** de identidad de la lista Permitir o bloquear inquilino reemplazan la funcionalidad de la directiva de inteligencia de suplantación de identidad que estaba disponible en la página de directivas contra correo no deseado en el Centro de cumplimiento de seguridad &.
>
>- La información de inteligencia de suplantación muestra 7 días de datos. El cmdlet **Get-SpoofIntelligenceInsight** muestra datos de 30 días.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la pestaña **Suplantación de** identidad en la página **Lista de inquilinos permitidos o bloqueados** , use <https://security.microsoft.com/tenantAllowBlockList?viewid=SpoofItem>. Para ir directamente a la página **Spoof intelligence insight (Información de inteligencia de suplantación** de identidad), use <https://security.microsoft.com/spoofintelligence>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para modificar la directiva de inteligencia de suplantación de identidad o habilitar o deshabilitar la inteligencia de suplantación de identidad, debe ser miembro de 
    -   **Administración de organizaciones**
    -   **Administrador de seguridad** <u>y</u> **Configuración de solo vista** o **Administración de la organización de solo vista**.
  - Para obtener acceso de solo lectura a la directiva de inteligencia de suplantación de identidad, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** .

  Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - La adición de usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Habilite y deshabilite la inteligencia de suplantación de identidad en las directivas contra suplantación de identidad en EOP y Microsoft Defender para Office 365. La inteligencia de suplantación de identidad está habilitada de forma predeterminada. Para obtener más información, vea [Configurar directivas contra suplantación de identidad en EOP](configure-anti-phishing-policies-eop.md) o [Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md).

- Para ver nuestra configuración recomendada para la inteligencia de suplantación de identidad, consulte Configuración de la [directiva de suplantación de identidad (EOP).](recommended-settings-for-eop-and-office365-atp.md#eop-anti-phishing-policy-settings)

## <a name="open-the-spoof-intelligence-insight-in-the-microsoft-365-defender-portal"></a>Abra la información de inteligencia sobre suplantación de identidad en el portal de Microsoft 365 Defender

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico &** Directivas de colaboración \> **& Directivas de amenazas**  \> de reglas \> **Listas de inquilinos permitidos o bloqueados** en la sección **Reglas**. Para ir directamente a la pestaña **Suplantación de** identidad en la página **Lista de inquilinos permitidos o bloqueados** , use <https://security.microsoft.com/tenantAllowBlockList?viewid=SpoofItem>.

2. En la página **Listas de permitidos o bloqueados** de inquilinos, la información de inteligencia de suplantación es similar a la siguiente:

   :::image type="content" source="../../media/m365-sc-spoof-intelligence-insight.png" alt-text="La información de inteligencia de suplantación de identidad en la página De la directiva contra suplantación de identidad" lightbox="../../media/m365-sc-spoof-intelligence-insight.png":::

   La información tiene dos modos:

   - **Modo de información**: si la inteligencia de suplantación está habilitada, la información muestra cuántos mensajes se detectaron mediante inteligencia suplantada durante los últimos siete días.
   - **Modo What if**: si la inteligencia de suplantación de identidad está deshabilitada, la información muestra cuántos mensajes *se habrían* detectado mediante la inteligencia de suplantación de identidad durante los últimos siete días.

Para ver información sobre las detecciones de inteligencia de suplantación de identidad, haga clic en **Ver actividad de suplantación** de identidad en la información de inteligencia de suplantación.

### <a name="view-information-about-spoofed-messages"></a>Visualización de información sobre mensajes suplantados

> [!NOTE]
> Recuerde que solo aparecen en esta página los remitentes suplantados detectados por inteligencia de suplantación de identidad. Al invalidar el veredicto de permitir o bloquear en la información, el remitente suplantado se convierte en una entrada manual de permitir o bloquear que aparece solo en la pestaña **Suplantación** de identidad en la lista de permitidos o bloqueados de inquilinos.

En la página **Información de inteligencia de** suplantación que aparece después de hacer clic en **Ver actividad de suplantación** de identidad en la información de inteligencia de suplantación, la página contiene la siguiente información:

- **Usuario suplantado**: **dominio** del usuario suplantado que se muestra en el cuadro **De** en los clientes de correo electrónico. La dirección From también se conoce como dirección `5322.From` .
- **Infraestructura de envío**: también conocida como _infraestructura_. La infraestructura de envío será uno de los siguientes valores:
  - Dominio encontrado en una búsqueda dns inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen.
  - Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\>/24 (por ejemplo, 192.168.100.100/24).
- **Recuento** de mensajes: el número de mensajes de la combinación del dominio suplantado _y_ la infraestructura de envío a la organización en los últimos 7 días.
- **Última vez que se ha visto**: la última fecha en que se recibió un mensaje de la infraestructura de envío que contiene el dominio suplantado.
- **Tipo de suplantación**: uno de los siguientes valores:
  - **Interno**: el remitente suplantado está en un dominio que pertenece a su organización (un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
  - **Externo**: el remitente suplantado está en un dominio externo.
- **Acción**: este valor es **Permitido** o **Bloqueado**:
  - **Permitido**: el dominio no pudo realizar comprobaciones de autenticación explícita de correo electrónico [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md) y [DMARC](use-dmarc-to-validate-email.md). Sin embargo, el dominio pasó nuestras comprobaciones implícitas de autenticación de correo electrónico ([autenticación compuesta](email-validation-and-authentication.md#composite-authentication)). Como resultado, no se realizó ninguna acción contra la suplantación de identidad en el mensaje.
  - **Bloqueado**: los mensajes de la combinación del dominio suplantado _y_ la infraestructura de envío están marcados como incorrectos por la inteligencia suplantada. La acción que se realiza en los mensajes suplantados se controla mediante la directiva de anti phishing predeterminada o las directivas de anti phishing personalizadas (el valor predeterminado es **Mover mensaje a la carpeta Correo no deseado**). Para obtener más información, consulte [Configuración de directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md).

Puede hacer clic en los encabezados de columna seleccionados para ordenar los resultados.

Para filtrar los resultados, tiene las siguientes opciones:

- Haga clic en el botón **Filtrar** . En el control flotante **Filtro** que aparece, puede filtrar los resultados por:
  - **Tipo de suplantación de identidad**
  - **Action**
- Use el cuadro **Buscar** para escribir una lista separada por comas de valores de dominio suplantados o enviar valores de infraestructura para filtrar los resultados.

### <a name="view-details-about-spoofed-messages"></a>Ver detalles sobre mensajes suplantados

Al seleccionar una entrada de la lista, aparece un control flotante de detalles que contiene la siguiente información y características:

- **Permitir suplantar** o **bloquear la suplantación** de identidad: seleccione uno de estos valores para invalidar el veredicto de inteligencia sobre suplantación de identidad original y mover la entrada de la información de inteligencia de suplantación a la lista de permitidos o bloques de inquilinos como entrada de permiso o de bloqueo para suplantación de identidad.
- Por qué lo capturamos.
- Lo que tienes que hacer.
- Un resumen de dominio que incluye la mayoría de la misma información de la página principal de inteligencia sobre suplantación de identidad.
- WhoIs datos sobre el remitente.
- Vínculo para abrir [el Explorador de amenazas](threat-explorer.md) para ver detalles adicionales sobre el remitente en **Ver** \> **phish** en Microsoft Defender para Office 365.
- Mensajes similares que hemos visto en el inquilino desde el mismo remitente.

### <a name="about-allowed-spoofed-senders"></a>Acerca de los remitentes suplantados permitidos

Un remitente suplantado permitido en la información de inteligencia de suplantación o un remitente falsificado bloqueado que ha cambiado manualmente a **Permitir la suplantación** solo permite mensajes de la combinación del dominio suplantado *y* la infraestructura de envío. No permite el correo electrónico del dominio suplantado de ningún origen ni permite el correo electrónico de la infraestructura de envío para ningún dominio.

Por ejemplo, el siguiente remitente suplantado puede suplantar:

- **Dominio**: gmail.com
- **Infraestructura**: tms.mx.com

Solo se permitirá la suplantación de correo electrónico de ese par de infraestructura de dominio o envío. No se permiten automáticamente otros remitentes que intenten suplantar gmail.com. Los mensajes de los remitentes de otros dominios que se originan en tms.mx.com siguen siendo comprobados por inteligencia de suplantación de identidad y pueden bloquearse.

## <a name="use-the-spoof-intelligence-insight-in-exchange-online-powershell-or-standalone-eop-powershell"></a>Uso de la información de inteligencia de suplantación de identidad en Exchange Online PowerShell o PowerShell de EOP independiente

En PowerShell, se usa el cmdlet **Get-SpoofIntelligenceInsight** para **ver** los remitentes suplantados permitidos y bloqueados detectados por la inteligencia de suplantación de identidad. Para permitir o bloquear manualmente los remitentes suplantados, debe usar el cmdlet **New-TenantAllowBlockListSpoofItems** . Para obtener más información, consulte [Uso de PowerShell para administrar entradas de remitente suplantadas en la lista de permitidos o bloqueados](tenant-allow-block-list.md) de inquilinos.

Para ver la información en la información de inteligencia de suplantación, ejecute el siguiente comando:

```powershell
Get-SpoofIntelligenceInsight
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Get-SpoofIntelligenceInsight](/powershell/module/exchange/get-spoofintelligenceinsight).

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Otras formas de administrar la suplantación de identidad y la suplantación de identidad (phishing)

Sea diligente sobre la suplantación de identidad y la protección contra suplantación de identidad (phishing). Estas son formas relacionadas de comprobar los remitentes que están suplantando el dominio y ayudar a evitar que dañen su organización:

- Compruebe el **informe de correo de suplantación de identidad**. Puede usar este informe a menudo para ver y ayudar a administrar remitentes suplantados. Para obtener información, vea [Informe de detecciones de suplantación de](view-email-security-reports.md#spoof-detections-report) identidad.

- Revise la configuración del Marco de directivas de remitente (SPF). Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [Configuración de SPF en Microsoft 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para comprender en detalle cómo Office 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Revise la configuración de Correo identificado con DomainKeys (DKIM). Debe usar DKIM además de SPF y DMARC para evitar que los atacantes envíen mensajes que parezcan procedentes de su dominio. DKIM le permite agregar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje. Para obtener información, consulte [Uso de DKIM para validar el correo electrónico saliente enviado desde el dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md).

- Revise la configuración de autenticación de mensajes, informes y conformidad basada en dominio (DMARC). Implementar DMARC con SPF y DKIM ofrece protección adicional contra el correo electrónico de suplantación de identidad. DMARC permite a los sistemas que reciben los correos determinar qué hacer con los mensajes enviados desde su dominio que no superan las comprobaciones SPF o DKIM. Para obtener información, consulte [Uso de DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md).
