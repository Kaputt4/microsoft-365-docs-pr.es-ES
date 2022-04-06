---
title: Mensajes de correo electrónico en cuarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la cuarentena en Exchange Online Protection (EOP) que contiene mensajes potencialmente peligrosos o no deseados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac2d1bf550fd340c1e94ed5f3503352b40ba6556
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682777"
---
# <a name="quarantined-email-messages-in-eop-and-defender-for-office-365"></a>Mensajes de correo electrónico en cuarentena en EOP y Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, la cuarentena está disponible para contener mensajes potencialmente peligrosos o no deseados.

Las directivas antimalware ponen automáticamente en cuarentena un mensaje si _se_ encuentra que los datos adjuntos contienen malware. Para obtener más información, vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).

De forma predeterminada, las policías contra correo no deseado ponen en cuarentena los mensajes de suplantación de identidad (phishing) y de elevada confianza, y entregan correo no deseado, correo no deseado de elevada confianza y mensajes de correo electrónico masivo a la carpeta correo no deseado del usuario. Sin embargo, también puede crear y personalizar directivas contra correo no deseado para poner en cuarentena el correo no deseado, el correo no deseado de alta confianza y los mensajes de correo electrónico masivo. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

Tanto los usuarios como los administradores pueden trabajar con mensajes en cuarentena:

- _Las directivas de_ cuarentena definen lo que los usuarios pueden hacer o no hacer en los mensajes en cuarentena en función del motivo por el que el mensaje se ha puesto en cuarentena (para las características admitidas). Las directivas de cuarentena predeterminadas aplican las funcionalidades históricas como se describe a continuación. Los administradores pueden crear y aplicar directivas de cuarentena personalizadas que definen capacidades menos restrictivas o más restrictivas para los usuarios, y también activar las notificaciones de cuarentena. Para más información, consulte [Políticas de cuarentena](quarantine-policies.md).

- Los administradores pueden trabajar con todos los tipos de mensajes en cuarentena para todos los usuarios. De forma predeterminada, solo los administradores pueden trabajar con mensajes que se han puesto en cuarentena como malware, phishing de elevada confianza o como resultado de reglas de flujo de correo (también conocidas como reglas de transporte). Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).

- De forma predeterminada, los usuarios pueden trabajar con mensajes en cuarentena donde son un destinatario y el mensaje se ha puesto en cuarentena como correo no deseado, correo electrónico masivo o suplantación de identidad (no phishing de elevada confianza). Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como usuario en EOP](find-and-release-quarantined-messages-as-a-user.md).

  Para evitar que los usuarios puedan administrar sus propios mensajes de suplantación de identidad en cuarentena, los administradores pueden asignar una directiva de cuarentena que deniegue el acceso a los mensajes en cuarentena del veredicto de filtrado de correo electrónico de suplantación de identidad ( **phishing)** en las directivas contra correo no deseado. Para obtener más información, vea [Asignar directivas de cuarentena en directivas contra correo no](quarantine-policies.md#anti-spam-policies) [deseadoCuadescuar.](quarantine-policies.md)

- Los administradores y los usuarios pueden notificar falsos positivos a Microsoft en cuarentena.

- El tiempo durante el que los mensajes en cuarentena se mantienen en cuarentena antes de que expiren varía en función del motivo por el que el mensaje se ha puesto en cuarentena. Las características que ponen en cuarentena los mensajes y sus períodos de retención correspondientes se describen en la tabla siguiente:

  |Motivo de la cuarentena:|Período de retención predeterminado|¿Personalizable?|Comentarios|
  |---|---|:---:|---|
  |Mensajes en cuarentena por directivas contra correo no deseado: correo no deseado, correo no deseado de elevada confianza, phishing, phishing de elevada confianza o masivo.|15 días: <ul><li>En la directiva contra correo no deseado predeterminada.</li><li>En las directivas contra correo no deseado que cree en PowerShell.</li></ul> <p> 30 días en directivas contra correo no deseado que cree en el portal Microsoft 365 Defender correo electrónico.|Sí|Puede configurar (inferior) este valor en directivas contra correo no deseado. Para obtener más información, consulte la opción Conservar **correo no** deseado en cuarentena durante estos días (_QuarantineRetentionPeriod_) en [Configure anti-spam policies](configure-your-spam-filter-policies.md).|
  |Mensajes en cuarentena por directivas anti phishing: suplantación de identidad en EOP; suplantación de usuario, suplantación de dominio o inteligencia de buzones en Defender para Office 365.|30 días|Sí|Este período de retención también se controla mediante la configuración Retener **correo no** deseado en cuarentena durante estos muchos días (_QuarantineRetentionPeriod_) en directivas **contra correo** no deseado. El período de retención que se usa es el valor de la primera directiva contra **correo** no deseado que coincida con la que se define el destinatario.|
  |Mensajes en cuarentena por directivas antimalware (mensajes de malware).|15 días|No||
  |Mensajes puestos en cuarentena por Caja fuerte de datos adjuntos en Defender para Office 365 (mensajes de malware).|15 días|No||
  |Mensajes en cuarentena por reglas de flujo de correo: la acción es **Entregar el mensaje a la cuarentena hospedada** (_cuarentena_).|30 días|No||
  |Archivos en cuarentena por Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams (archivos de malware).|15 días|No||

  Cuando un mensaje expira de la cuarentena, no se puede recuperar.

Para obtener más información acerca de la cuarentena, consulta [Preguntas más frecuentes sobre cuarentena](quarantine-faq.yml).
