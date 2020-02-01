---
title: 'Purga automática cero horas: protección contra correo no deseado y malware'
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: La depuración automática de cero horas (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con correo no deseado o malware que ya se han entregado a los buzones de los usuarios y, a continuación, inofensivos en el contenido malintencionado. Cómo hace ZAP esto depende del tipo de contenido malintencionado detectado.
ms.openlocfilehash: 6616281a98487c7edd7ca7721ade9a8510f6a21f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597967"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Purga automática cero horas: protección contra correo no deseado y malware

## <a name="overview"></a>Información general

La purga automática de cero horas (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con phish, correo no deseado o malware que ya se han entregado a los buzones de los usuarios y, a continuación, inofensivos en el contenido malintencionado. Cómo hace ZAP esto depende del tipo de contenido malintencionado detectado. El correo se puede zapped debido al contenido de correo, las direcciones URL o los datos adjuntos.

ZAP está disponible con la protección de Exchange Online predeterminada que se incluye con cualquier suscripción a Office 365 que contenga buzones de correo de Exchange Online.

## <a name="how-zap-works"></a>Cómo funciona el ZAP

Office 365 actualiza las firmas de malware y del motor de correo no deseado en tiempo real de manera diaria. Sin embargo, es posible que los usuarios sigan teniendo mensajes malintencionados entregados a sus bandejas de correo por diversos motivos, incluso si el contenido se ha armado después de que se entregue a los usuarios. ZAP soluciona el control continuado de las actualizaciones de las firmas de correo no deseado y malware de Office 365. ZAP puede buscar y quitar los mensajes previamente entregados que ya se encuentran en las bandejas de los usuarios.

La acción ZAP es fluida para el usuario del buzón de correo; no se notifica si se mueve un mensaje de correo electrónico. 

Las listas de permitidos, [las reglas de flujo de correo](use-transport-rules-to-configure-bulk-email-filtering.md) (también conocidas como reglas de transporte) y las reglas de usuario final o los filtros adicionales tienen prioridad sobre Zap.

### <a name="malware-zap"></a>ZAP de malware

Para el malware recién detectado, ZAP mueve el mensaje completo, incluidos sus datos adjuntos, a la cuarentena de malware. Los mensajes se mueven independientemente del estado de lectura del correo. Si obtenemos una señal de malware para un mensaje en el proceso de análisis de entregas dinámicos, ZAP llevará a la acción de correo no deseado en el mensaje. A continuación, permitirá la entrega dinámica para finalizar el tiempo de análisis de entrega y realizar la acción correspondiente.

ZAP de malware está habilitado de forma predeterminada en la Directiva de malware. Puede deshabilitar el servicio ZAP de malware mediante el parámetro *ZapEnabled* en el cmdlet [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) de PowerShell de Exchange online o Exchange Online Protection. ZAP de malware también se puede habilitar o deshabilitar editando la Directiva de malware en el centro de seguridad y cumplimiento.

### <a name="phish-zap"></a>ZAP de phish

Para el correo que se identifica como phish después de la entrega, ZAP realiza una acción según la Directiva de correo no deseado que cubre a un usuario específico, independientemente del estado de lectura del correo. Si la acción de phish a directivas está configurada para *no* llevar a cabo la acción (agregar encabezado X, modificar asunto, sin acción), ZAP no llevará a cabo ninguna acción en el correo. Si se establece que la acción de phish se mueva a correo no deseado, ZAP moverá el mensaje a la carpeta correo no deseado de la bandeja de entrada del usuario. **Para cualquier otra acción de Phish (redirigir, eliminar, poner en cuarentena) Zap moverá el mensaje a cuarentena de phish**. Lea a continuación para conocer los requisitos de configuración y las exclusiones. Obtenga más información sobre cómo [configurar las directivas de filtro de correo no deseado](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) aquí.

La ZAP de phish está habilitada de forma predeterminada en la Directiva de correo no deseado. La ZAP de phish puede deshabilitarse con el parámetro *PhishZapEnabled* de [set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), un cmdlet de EOP.

### <a name="spam-zap"></a>ZAP de correo no deseado

Para el correo identificado como correo no deseado después de la entrega, ZAP realiza la acción según la Directiva de correo no deseado que cubre al usuario específico, sólo si el mensaje es no leído.  Si la acción de la Directiva de correo no deseado se establece en no realizar ninguna acción (agregar encabezado X, modificar asunto, sin acción), ZAP no llevará a cabo ninguna acción en el correo. Si se establece que la acción de correo no deseado se mueva a correo no deseado, ZAP moverá el mensaje a la carpeta correo no deseado de la bandeja de entrada del usuario. **Para cualquier otra acción de correo no deseado (redirigir, eliminar, poner en cuarentena) Zap moverá el mensaje a la cuarentena de correo no deseado**. Lea a continuación para conocer los requisitos de configuración y las exclusiones. Obtenga más información sobre cómo [configurar las directivas de filtro de correo no deseado](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) aquí.

La ZAP de correo no deseado está habilitada de forma predeterminada en la Directiva de correo no deseado. Puede deshabilitar el ZAP de correo no deseado mediante el parámetro *SpamZapEnabled* del cmdlet [set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) en PowerShell de Exchange online o Exchange Online Protection.

### <a name="phish-and-spam-zap-requirements-exclusions-and-notices"></a>Requisitos, exclusiones y avisos de los mensajes de correo no deseado de phish

> [!IMPORTANT]
> el parámetro de cmdlet *ZapEnabled* anterior, controlado tanto phish como de correo no deseado, no estará en **desuso, 1 de febrero de 2020**. Si ha escrito scripts que usan el parámetro ZapEnabled, se recomienda actualizarlos para que usen SpamZapEnabled y PhishZapEnabled. En el período transitorio, todos los tres parámetros (ZapEnabled, PhishZapEnabled y SpamZapEnabled) estarán disponibles a través del cmdlet. Hasta que se establezca explícitamente a través de la interfaz de usuario o PowerShell, PhishZapEnabled y SpamZapEnabled mostrarán un valor heredado del parámetro ZapEnabled. Una vez que se establecen los nuevos parámetros, ya no se heredarán del parámetro ZapEnabled. Una vez desusado, la configuración de ZapEnabled no tendrá ningún efecto en las propiedades PhishZapEnabled o SpamZapEnabled, y ZapEnabled se quitará de la lista de parámetros de los cmdlets.

ZAP no moverá ningún mensaje a cuarentena que esté en proceso de análisis de entregas dinámicos o que ya tenga un veredicto de malware con un dato adjunto reemplazado. Si se recibe una señal de phish o correo no deseado para estos tipos de mensajes y la acción de directiva o phish de correo no deseado está configurada para realizar alguna acción (mover a correo no deseado, redirigir, eliminar, cuarentena), el valor de ZAP será la acción "mover a correo no deseado". Para que ZAP lleve a cabo la acción ' mover a correo no deseado ' en un mensaje, el usuario debe tener habilitada la protección contra correo electrónico no deseado, con la configuración predeterminada de correo no deseado. (Consulte [cambiar el nivel de protección en el filtro de correo no deseado](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) para obtener más información acerca de las opciones de usuario en Outlook).

## <a name="how-to-see-if-zap-moved-your-message"></a>Cómo ver si el ZAP movió el mensaje

Para determinar si la ZAP movió el mensaje, puede usar el informe de estado de la [protección contra amenazas](view-email-security-reports.md#threat-protection-status-report) o el [Explorador de amenazas (y detecciones en tiempo real)](threat-explorer.md). Tenga en cuenta que, como acción del sistema, ZAP no se registra en los registros de auditoría de buzones de Exchange. 
 
## <a name="disable-zap"></a>Deshabilitar ZAP

Para conectarse al PowerShell de Exchange Online, consulte [Conectarse al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para conectarse a PowerShell de Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

### <a name="disable-malware-zap"></a>Deshabilitar el ZAP de malware * *

ZAP de malware puede deshabilitarse a través del parámetro *ZapEnabled* en el cmdlet [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) en Exchange Online PowerShell o Exchange Online Protection PowerShell. ZAP de malware también se puede habilitar o deshabilitar editando la Directiva de malware en el centro de seguridad y cumplimiento.

En este ejemplo se deshabilita ZAP en la Directiva de filtro de malware denominada "Test".

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).

### <a name="disable-phish-zap-and-spam-zap"></a>Deshabilitar el Zap de robo de phish y correo no deseado

Para deshabilitar la ZAP de phish y correo no deseado para el inquilino de O365 o un conjunto de usuarios, use los parámetros *PhishZapEnabled* y *SpamZapEnabled* de [set-HOSTEDCONTENTFILTERPOLICY](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), un cmdlet de EOP.

En el siguiente ejemplo, se deshabilita phish y spam de correo no deseado para una directiva de filtro de contenido denominada "Test".

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy).

## <a name="faq"></a>Preguntas frecuentes

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>¿Qué sucede si un mensaje legítimo se mueve a la carpeta correo no deseado?

Debe seguir el proceso normal de informes para [falsos positivos](prevent-email-from-being-marked-as-spam.md). La única razón por la que el mensaje se movería de la bandeja de entrada a la carpeta correo no deseado sería porque el servicio determinó que el mensaje era correo no deseado o malintencionado.

### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>¿Qué ocurre si utilizo la cuarentena de Office 365 en lugar de la carpeta de correo no deseado?

ZAP emprenderá acciones de acuerdo con la configuración de las opciones de la acción phish y correo no deseado en la Directiva contra correo no deseado. Para obtener más información sobre malware, phish y correo no deseado, vea más arriba.

### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>¿Qué ocurre si tengo una regla de flujo de correo personalizada (regla de bloqueo/permiso)?

Las reglas creadas por los administradores (reglas de flujo de correo) o las reglas de bloqueo y permiso tienen prioridad. Estos mensajes se excluyen de los criterios de la característica, por lo que el flujo de correo seguirá la acción de regla (bloquear/permitir regla).

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>¿Qué ocurre si un mensaje se mueve a otra carpeta (por ejemplo, una regla de bandeja de entrada)?

ZAP sigue funcionando en este caso, a menos que el mensaje se haya eliminado o esté en correo no deseado.

### <a name="does-zap-change-the-email-header"></a>¿ZAP cambia el encabezado del correo electrónico?

Una acción ZAP no realiza ningún cambio en el encabezado de un correo electrónico.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>¿Cómo afecta el ZAP a los buzones en retención?

ZAP no quitará los mensajes de los buzones en retención y, por lo tanto, no se podrá mover a la acción de cuarentena en los mensajes. Los mensajes se moverán a la carpeta de correo no deseado si así lo especifica la Directiva. 

[Haga clic aquí para obtener más información sobre las suspensiones de buzones.](https://docs.microsoft.com/exchange/policy-and-compliance/holds/holds?view=exchserver-2019)

## <a name="related-topics"></a>Temas relacionados

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)

[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](reduce-spam-email.md)
