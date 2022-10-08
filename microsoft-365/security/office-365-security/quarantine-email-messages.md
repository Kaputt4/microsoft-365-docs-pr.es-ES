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
- m365-security
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la cuarentena en Exchange Online Protection (EOP) que contiene mensajes potencialmente peligrosos o no deseados.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 000b6d37dea1280371bef2a2e32e9c2b5e61383c
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68091749"
---
# <a name="quarantined-email-messages-in-eop-and-defender-for-office-365"></a>Mensajes de correo electrónico en cuarentena en EOP y Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, la cuarentena está disponible para contener mensajes potencialmente peligrosos o no deseados.

Las directivas antimalware ponen automáticamente en cuarentena un mensaje si se encuentra _algún_ dato adjunto que contenga malware. Para obtener más información, vea [Configurar directivas antimalware en EOP](configure-anti-malware-policies.md).

De forma predeterminada, las directivas contra correo no deseado ponen en cuarentena los mensajes de suplantación de identidad (phishing) y los mensajes de suplantación de identidad (phishing) de alta confianza, y entregan mensajes de correo no deseado, correo no deseado de alta confianza y mensajes de correo electrónico masivos a la carpeta junk Email del usuario. Sin embargo, también puede crear y personalizar directivas de correo no deseado para poner en cuarentena el correo no deseado, el correo no deseado de alta confianza y los mensajes de correo electrónico masivo. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

Tanto los usuarios como los administradores pueden trabajar con mensajes en cuarentena:

- _Las directivas de cuarentena_ definen qué usuarios pueden hacer o no en los mensajes en cuarentena en función de por qué se puso en cuarentena el mensaje (para las características admitidas). Las directivas de cuarentena predeterminadas aplican las funcionalidades históricas como se describe a continuación. Los administradores pueden crear y aplicar directivas de cuarentena personalizadas que definan funcionalidades menos restrictivas o más restrictivas para los usuarios, y también activen las notificaciones de cuarentena. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).

- Los administradores pueden trabajar con todos los tipos de mensajes en cuarentena para todos los usuarios. De forma predeterminada, solo los administradores pueden trabajar con mensajes que se pusieron en cuarentena como malware, suplantación de identidad de alta confianza o como resultado de reglas de flujo de correo (también conocidas como reglas de transporte). Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).

- De forma predeterminada, los usuarios pueden trabajar con mensajes en cuarentena donde son un destinatario y el mensaje se puso en cuarentena como correo no deseado, correo electrónico masivo o suplantación de identidad (no suplantación de identidad de alta confianza). Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como usuario en EOP](find-and-release-quarantined-messages-as-a-user.md).

  Para evitar que los usuarios administren sus propios mensajes de suplantación de identidad (phishing) en cuarentena, los administradores pueden asignar una directiva de cuarentena que deniegue el acceso a los mensajes en cuarentena desde el veredicto de filtrado de **correo electrónico de phishing** en las directivas contra correo no deseado. Para obtener más información, consulte [Asignación de directivas de cuarentena en directivas de cuarentena contra correo no deseado](quarantine-policies.md#anti-spam-policies)[](quarantine-policies.md).

- Los administradores y los usuarios pueden notificar falsos positivos a Microsoft en cuarentena.

- El tiempo que los mensajes en cuarentena se mantienen en cuarentena antes de que expiren varía en función del motivo por el que el mensaje se puso en cuarentena. Las características que ponen en cuarentena los mensajes y sus períodos de retención correspondientes se describen en la tabla siguiente:

  |Motivo de la cuarentena:|Período de retención predeterminado|¿Personalizable?|Comentarios|
  |---|---|:---:|---|
  |Mensajes en cuarentena por directivas antispam: correo no deseado, spam de alta confianza, suplantación de identidad (phishing), suplantación de identidad (phishing) de alta confianza o de forma masiva.|15 días: <ul><li>En la directiva de antispam predeterminada.</li><li>En las directivas contra correo no deseado que se crean en PowerShell.</li></ul> <p> 30 días en las directivas contra correo no deseado que cree en el portal de Microsoft 365 Defender.|Yes|Puede configurar (inferior) este valor en las directivas contra correo no deseado. Para obtener más información, consulte la configuración **Retener correo no deseado en cuarentena para estos muchos días** (_QuarantineRetentionPeriod_) en [Configurar directivas de antispam](configure-your-spam-filter-policies.md).|
  |Mensajes en cuarentena por directivas anti phishing: inteligencia de suplantación de identidad en EOP; suplantación de usuario, suplantación de dominio o inteligencia de buzón de correo en Defender para Office 365.|30 días|Sí|Este período de retención también se controla mediante la configuración **Retener correo no deseado en cuarentena durante estos muchos días** (_QuarantineRetentionPeriod_) en las **directivas de antispam** . El período de retención que se usa es el valor de la primera directiva **antispam** coincidente en la que se define el destinatario.|
  |Mensajes en cuarentena por directivas antimalware (mensajes de malware).|30 días|No||
  |Mensajes en cuarentena por directivas de datos adjuntos seguros en Defender para Office 365 (mensajes de malware).|30 días|No||
  |Mensajes en cuarentena por reglas de flujo de correo: la acción es **Entregar el mensaje a la cuarentena hospedada** (_cuarentena_).|30 días|No||
  |Archivos en cuarentena por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams (archivos de malware).|30 días|No|Los archivos en cuarentena en SharePoint o OneDrive se quitan de la cuarentena de fom después de 30 días, pero los archivos bloqueados permanecen en SharePoint o OneDrive en estado bloqueado.|

  Cuando un mensaje expira de la cuarentena, no se puede recuperar.

Para obtener más información sobre la cuarentena, consulte [Preguntas más frecuentes sobre cuarentena](quarantine-faq.yml).
