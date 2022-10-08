---
title: ¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- m365-security
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender sobre las diferencias entre correo no deseado (correo no deseado) y correo electrónico masivo (correo gris) en Exchange Online Protection (EOP).
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 6613502c858a87096b4220b17d94b8821b0f9835
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68066154"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>¿Cuál es la diferencia entre el correo electrónico no deseado y el correo electrónico masivo en EOP?

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin Exchange Online buzones, los clientes a veces preguntan: "¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?" En este tema se explica la diferencia y se describen los controles que están disponibles en EOP.

- **El correo no deseado** es correo no deseado, que son mensajes no solicitados y universalmente no deseados (cuando se identifican correctamente). De forma predeterminada, el EOP rechaza el correo no deseado en función de la reputación del servidor de correo electrónico de origen. Si un mensaje pasa la inspección de ip de origen, se envía al filtrado de correo no deseado. Si el mensaje se clasifica como correo no deseado mediante el filtrado de correo no deseado, el mensaje se entrega (de forma predeterminada) a los destinatarios previstos y se mueve a su carpeta De correo no deseado Email.

  - Puede configurar las acciones que se llevarán a cabo en los veredictos de filtrado de correo no deseado. Para obtener instrucciones, consulte [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

  - Si no está de acuerdo con el veredicto de filtrado de correo no deseado, puede notificar a Microsoft los mensajes que considere como correo no deseado o no spam de varias maneras, como se describe en [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- **El correo electrónico masivo** (también conocido como _correo gris_) es más difícil de clasificar. Mientras que el correo no deseado es una amenaza constante, el correo electrónico masivo suele ser anuncios únicos o mensajes de marketing. Algunos usuarios quieren mensajes de correo electrónico masivos (y de hecho, se han registrado deliberadamente para recibirlos), mientras que otros usuarios consideran que el correo electrónico masivo es correo no deseado. Por ejemplo, algunos usuarios quieren recibir mensajes publicitarios de Contoso Corporation o invitaciones a una próxima conferencia sobre ciberseguridad, mientras que otros usuarios consideran que estos mismos mensajes son correo no deseado.

  Para obtener más información sobre cómo se identifica el correo electrónico masivo, consulte [Nivel de quejas masivas (BCL) en EOP](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Cómo administrar el correo masivo

Debido a la reacción mixta al correo electrónico masivo, no hay una guía universal que se aplique a todas las organizaciones.

Las directivas contra correo no deseado tienen un umbral de BCL predeterminado que se usa para identificar el correo electrónico masivo como correo no deseado. Los administradores pueden aumentar o reducir el umbral. Para obtener más información, consulte los siguientes temas:

- [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).
- [Configuración de directivas contra correo no deseado de EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

Otra opción fácil de pasar por alto: si un usuario se queja de recibir correo electrónico masivo, pero los mensajes proceden de remitentes de confianza que pasan el filtrado de correo no deseado en EOP, haga que el usuario compruebe si hay una opción de cancelación de suscripción en el mensaje de correo electrónico masivo.

## <a name="how-to-tune-bulk-email"></a>Cómo optimizar el correo electrónico masivo

En septiembre de 2022, los clientes de Microsoft Defender para Office 365 Plan 2 pueden acceder a BCL desde [la búsqueda avanzada](/microsoft-365/security/defender/advanced-hunting-overview). Esta característica permite a los administradores examinar todos los remitentes masivos que enviaron correo a su organización, junto con los valores de BCL correspondientes y el volumen de correo electrónico recibido. Puede explorar en profundidad los remitentes masivos mediante otras columnas de la tabla **EmailEvents** del esquema **de colaboración Email &**. Para obtener más información, vea [EmailEvents](/microsoft-365/security/defender/advanced-hunting-emailevents-table).

Por ejemplo, si Contoso ha establecido su umbral masivo actual en 7 en las directivas contra correo no deseado, los destinatarios de Contoso recibirán correo electrónico de todos los remitentes con BCL \< 7 en su Bandeja de entrada. Los administradores pueden ejecutar la siguiente consulta para obtener una lista de todos los remitentes masivos de la organización:

```console
EmailEvents
| where BulkComplaintLevel >= 1 and Timestamp > datetime(2022-09-XXT00:00:00Z)
| summarize count() by SenderMailFromAddress, BulkComplaintLevel
```

Esta consulta permite a los administradores identificar remitentes deseados y no deseados. Si un remitente masivo tiene una puntuación de BCL que no cumple el umbral masivo, los administradores pueden [enviar los mensajes del remitente a Microsoft para su análisis](allow-block-email-spoof.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal), lo que agrega el remitente como una entrada permitida a la lista de inquilinos permitidos o bloqueados.

Las organizaciones sin Defender para Office 365 Plan 2 pueden probar las características de Microsoft 365 Defender para Office 365 Plan 2 de forma gratuita. Use la evaluación de Defender para Office 365 de 90 días en <https://security.microsoft.com/atpEvaluation>. Obtenga información sobre quién puede registrarse y probar los términos [aquí](try-microsoft-defender-for-office-365.md) o puede usar el [informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report) para identificar remitentes masivos deseados y no deseados:

1. En el informe Estado de protección contra amenazas, seleccione **Ver datos Email \> Correo no deseado**. Para ir directamente al informe, abra una de las siguientes direcciones URL:

   - EOP: <https://security.microsoft.com/reports/TPSAggregateReport>
   - Defender para Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP>

2. Filtre por correo electrónico masivo, seleccione un correo electrónico para investigar y haga clic en la entidad de correo electrónico para obtener más información sobre el remitente. Email entidad solo está disponible para clientes de Defender para Office 365 Plan 2.

3. Una vez que haya identificado remitentes deseados y no deseados, ajuste el umbral masivo al nivel deseado. Si hay remitentes masivos con puntuación BCL que no caben dentro del umbral masivo, [envíe los mensajes a Microsoft para su análisis](allow-block-email-spoof.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal), lo que agrega el remitente como una entrada permitida a la lista de inquilinos permitidos o bloqueados.

Los administradores pueden seguir los [valores de umbral masivo recomendados](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365.md#anti-spam-anti-malware-and-anti-phishing-protection-in-eop) o elegir un valor de umbral masivo que se adapte a las necesidades de su organización.
