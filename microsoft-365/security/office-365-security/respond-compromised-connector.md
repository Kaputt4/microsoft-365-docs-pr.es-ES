---
title: Respuesta a un conector en peligro en Microsoft 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- m365-security
ms.custom: ''
description: Aprenda a reconocer y responder a un conector en peligro en Microsoft 365.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 8ce206393c489ab162f8bdaf74e906beaf69e4ed
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68079851"
---
# <a name="respond-to-a-compromised-connector"></a>Responder a un conector en peligro

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**

- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Los conectores se usan para habilitar el flujo de correo entre Microsoft 365 o Office 365 y los servidores de correo electrónico que tiene en el entorno local. Para obtener más información, vea [Configurar el flujo del correo mediante conectores en Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

Un conector de entrada en peligro se define como cuando una persona no autorizada aplica los cambios a un conector de entrada existente o crea un nuevo conector de entrada en un inquilino de Microsoft 365, con la intención de enviar correos electrónicos no deseados o de correo no deseado. Tenga en cuenta que esto solo se aplica a los conectores entrantes de tipo OnPremises. 

## <a name="detect-a-compromised-connector"></a>Detección de un conector en peligro

Estas son algunas de las características de un conector en peligro:

- Aumento repentino del volumen de correo saliente. 

- Discrepancia entre los remitentes P1 y P2 en los correos salientes. Para obtener más información sobre los remitentes P1 y P2, vea [Cómo EOP valida la dirección Desde para evitar la suplantación de identidad (phishing](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)).

- Correos salientes enviados desde un dominio que no está aprovisionado ni registrado. 

- El conector no puede enviar correo de retransmisión. 

- El usuario previsto o el administrador no crearon la presencia de un conector de entrada. 

- Cambios no autorizados en la configuración del conector existente, como el nombre, el nombre de dominio y la dirección IP. 

- Una cuenta de administrador en peligro recientemente. Tenga en cuenta que solo puede editar la configuración del conector si tiene acceso administrativo. 

## <a name="secure-and-restore-email-function-to-a-suspected-compromised-connector"></a>Protección y restauración de la función de correo electrónico en un conector sospechoso en peligro

Debe completar todos los pasos siguientes para recuperar el acceso al conector. Estos pasos le ayudarán a quitar las entradas de puerta trasera que se hayan agregado al conector.

### <a name="step-1-identify-if-an-inbound-connector-has-been-compromised"></a>Paso 1: Identificar si un conector de entrada se ha puesto en peligro 

#### <a name="review-recent-suspicious-connector-traffic-or-related-messages"></a>Revisión del tráfico de conector sospechoso reciente o los mensajes relacionados

Si tiene [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md), vaya directamente a https://security.microsoft.com/threatexplorer. 

1. Seleccione **Conector**, inserte **Nombre del conector**, seleccione Intervalo de fechas y, a continuación, haga clic en **Actualizar**. 

    :::image type="content" source="../../media/connector-compromise-explorer.png" alt-text="Vista del explorador del conector de entrada" lightbox="../../media/connector-compromise-explorer.png":::

2. Identifique si hay algún pico o caída anómalo en el tráfico de correo electrónico.

    :::image type="content" source="../../media/connector-compromise-abnormal-spike.png" alt-text="Número de correos electrónicos entregados a la carpeta de correo no deseado" lightbox="../../media/connector-compromise-abnormal-spike.png":::

3. Identificar: 

    - Si **la dirección IP del remitente** coincide con la dirección IP local de la organización. 

    - Si recientemente se envió un número significativo de correos electrónicos a la carpeta **Correo no deseado** . Este es un buen indicador de un conector en peligro que se usa para enviar correo no deseado. 

    - Si los destinatarios son los que su organización suele mantenerse en contacto. 

    :::image type="content" source="../../media/connector-compromise-sender-ip.png" alt-text="Dirección IP del remitente y la dirección IP local de la organización" lightbox="../../media/connector-compromise-sender-ip.png":::

Si tiene [Microsoft Defender para Office 365 plan 1](defender-for-office-365.md) o [Exchange Online Protection](exchange-online-protection-overview.md), vaya a https://admin.exchange.microsoft.com/#/messagetrace. 

1. Abra **la alerta de actividad sospechosa del conector** en https://security.microsoft.com/alerts.  

2. Seleccione una actividad en **Lista de actividad** y copie el **dominio del conector** sospechoso y la **dirección IP** detectadas en la alerta.

    :::image type="content" source="../../media/connector-compromise-outbound-email-details.png" alt-text="Detalles del correo electrónico saliente en peligro del conector" lightbox="../../media/connector-compromise-outbound-email-details.png":::
    
3. Busque mediante **el dominio del conector** y **la dirección IP** en [**Seguimiento de mensajes**](https://admin.exchange.microsoft.com/#/messagetrace). 

    :::image type="content" source="../../media/connector-compromise-new-message-trace.png" alt-text="Nuevo control flotante de seguimiento de mensajes" lightbox="../../media/connector-compromise-new-message-trace.png":::
    
4. En los resultados de la búsqueda **de seguimiento de** mensajes, identifique: 

    - Si un número significativo de correos electrónicos se marcaron recientemente como **FilteredAsSpam**. Este es un buen indicador de un conector en peligro que se usa para enviar correo no deseado. 

    - Si los destinatarios son los que su organización suele mantenerse en contacto. 

    :::image type="content" source="../../media/connector-compromise-message-trace-results.png" alt-text="Nuevos resultados de búsqueda de seguimiento de mensajes" lightbox="../../media/connector-compromise-message-trace-results.png":::

#### <a name="investigate-and-validate-connector-related-activity"></a>Investigación y validación de la actividad relacionada con el conector 

Use la siguiente línea de comandos en PowerShell para investigar y validar la actividad relacionada con el conector por parte de un usuario en el registro de auditoría. Para obtener más información, consulte [Uso de un script de PowerShell para buscar en el registro de auditoría](/compliance/audit-log-search-script). 

```powershell
Search-UnifiedAuditLog -StartDate "<ExDateTime>" -EndDate "<ExDateTime>" -Operations "New-InboundConnector", "Set-InboundConnector", "Remove-InboundConnector
```

### <a name="step-2-review-and-revert-unauthorized-changes-in-a-connector"></a>Paso 2: Revisar y revertir los cambios no autorizados en un conector 

1. Inicie sesión en https://admin.exchange.microsoft.com/. 

2. Revise y revierta los cambios no autorizados del conector. 

### <a name="step-3-unblock-the-connector-to-re-enable-mail-flow"></a>Paso 3: Desbloquear el conector para volver a habilitar el flujo de correo 

1. Inicie sesión en https://security.microsoft.com/restrictedentities. 

2. Seleccione el conector restringido para desbloquear el conector. 

### <a name="step-4-investigate-and-remediate-potentially-compromised-administrative-user-account"></a>Paso 4: Investigación y corrección de una cuenta de usuario administrativa potencialmente en peligro

Si se identifica un usuario con una actividad de conector no autorizada, puede investigar a este usuario para detectar posibles riesgos. Para obtener más información, vea [Responder a una cuenta de correo electrónico en peligro](responding-to-a-compromised-email-account.md).

## <a name="more-information"></a>Más información

- [Quitar conectores bloqueados](remove-blocked-connectors.md)
- [Quitar usuarios bloqueados](removing-user-from-restricted-users-portal-after-spam.md)
