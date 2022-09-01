---
title: Proteger de forma predeterminada en Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Más información sobre la configuración segura de forma predeterminada en Exchange Online Protection (EOP)
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: b70e3639df2cfa1b2099cc5e61efe43b216b4afe
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497321"
---
# <a name="secure-by-default-in-office-365"></a>Proteger de forma predeterminada en Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"Seguro de forma predeterminada" es un término que se usa para definir la configuración predeterminada más segura posible.

Sin embargo, la seguridad debe estar equilibrada con la productividad. Esto puede incluir el equilibrio entre:

- **Facilidad de uso**: la configuración no debería interponerse en el camino de la productividad del usuario.
- **Riesgo**: la seguridad podría bloquear actividades importantes.
- **Configuración heredada**: es posible que sea necesario mantener algunas configuraciones de productos y características anteriores por motivos empresariales, aunque se mejore la configuración moderna nueva.

Microsoft 365 organizaciones con buzones en Exchange Online están protegidas por Exchange Online Protection (EOP). La protección incluye:

- Email con sospecha de malware se pondrá automáticamente en cuarentena. La directiva de cuarentena y la configuración de la directiva antimalware controlan si los destinatarios reciben una notificación sobre los mensajes de malware en cuarentena. Para obtener más información, vea [Configurar directivas antimalware en EOP](configure-anti-malware-policies.md).
- El correo electrónico identificado como suplantación de identidad de alta confianza se controlará según la acción de la directiva contra correo no deseado. Consultar [Configuración de las directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

Para obtener más información sobre EOP, consulte [Información general de Exchange Online Protection](exchange-online-protection-overview.md)

Debido a que Microsoft quiere mantener seguros a nuestros clientes de forma predeterminada, algunas anulaciones de inquilinos no se aplican para malware o phishing de alta confianza. Estas anulaciones incluyen:

- Listas de remitentes permitidos o listas de dominios permitidos (directivas contra correo no deseado)
- Remitentes seguros de Outlook
- Lista de direcciones IP permitidas (filtrado de conexiones)
- Reglas de flujo de correo de Exchange (también conocidas como reglas de transporte)

Puede encontrar más información sobre estas invalidaciones en [Crear listas de remitentes seguros](create-safe-sender-lists-in-office-365.md).

> [!NOTE]
> Hemos dejado de usar la acción **Mover mensaje a correo no deseado** acción para un **correo electrónico de suplantación de identidad de alta confianza** veredicto en las directivas contra correo no deseado de EOP. Las directivas contra correo no deseado que usan esta acción para mensajes de suplantación de identidad de alta confianza se convertirán en **mensaje en cuarentena**. El mensaje de redirección **a la dirección de correo electrónico** acción para mensajes de suplantación de identidad de alta confianza no se ve afectada.

La protección de forma predeterminada no es una configuración que se pueda activar o desactivar, pero es la forma en que nuestro filtrado funciona de forma predeterminada para mantener mensajes potencialmente peligrosos o no deseados fuera de los buzones. Los mensajes de suplantación de identidad (phishing) de alto nivel y malware deben estar en cuarentena. De forma predeterminada, solo los administradores pueden administrar mensajes que se ponen en cuarentena como malware o phishing de alta confianza, y también pueden notificar falsos positivos a Microsoft desde allí. Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).

## <a name="more-on-why-were-doing-this"></a>Más información sobre por qué estamos haciendo esto

El espíritu de ser seguro de forma predeterminada es: estamos realizando la misma acción en el mensaje que tomaría si sabía que el mensaje era malintencionado, incluso cuando una excepción configurada permitiría de otro modo que se entregara el mensaje. Este es el mismo enfoque que siempre hemos usado en malware y ahora estamos ampliando este mismo comportamiento a mensajes de suplantación de identidad de alta confianza.

Nuestros datos indican que es 30 veces más probable que un usuario haga clic en un vínculo malintencionado en los mensajes de la carpeta Correo no deseado frente a Cuarentena. Nuestros datos también indican que la tasa de falsos positivos (mensajes buenos marcados como incorrectos) para los mensajes de suplantación de identidad de alta confianza es muy baja y los administradores pueden resolver los falsos positivos con envíos de administradores.

También hemos determinado que el remitente permitido y las listas de dominios permitidos en las directivas contra correo no deseado y los remitentes seguros en Outlook eran demasiado amplios y provocaban más daños que buenos.

Dicho de otro modo: como servicio de seguridad, estamos actuando en su nombre para evitar que los usuarios se vean comprometidos.

## <a name="exceptions"></a>Excepciones

Solo debe considerar el uso de invalidaciones en los escenarios siguientes:

- Simulaciones de phishing: los ataques simulados pueden ayudarle a identificar usuarios vulnerables antes de que un ataque real afecte a su organización. Para evitar que los mensajes de simulación de suplantación de identidad (phishing) se filtren, consulte [Configuración de simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada](/microsoft-365/security/office-365-security/configure-advanced-delivery#use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy).
- Buzones de seguridad/SecOps: buzones dedicados que usan los equipos de seguridad para obtener mensajes sin filtrar (tanto buenos como incorrectos). A continuación, Los equipos pueden revisar para ver si contienen contenido malintencionado. Para obtener más información, vea [Configurar buzones de SecOps en la directiva de entrega avanzada](/microsoft-365/security/office-365-security/configure-advanced-delivery#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy).
- Filtros de terceros: la protección de forma predeterminada solo se aplica cuando el registro MX del dominio está establecido en Exchange Online Protection (contoso.mail.protection.outlook.com). Si se establece en otro servicio o dispositivo, es posible invalidar Secure de forma predeterminada con una [regla de transporte](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl) para omitir todo el filtrado de correo no deseado. Cuando Microsoft detecta mensajes como Phish de confianza alta con esta regla en vigor, siguen entregando a la Bandeja de entrada. 
- Falsos positivos: puede permitir temporalmente determinados mensajes que Microsoft [sigue analizando a través de envíos de administradores](admin-submission.md). Al igual que con todas las invalidaciones, se recomienda que sean temporales.
