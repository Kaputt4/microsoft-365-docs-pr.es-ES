---
title: Proteger de forma predeterminada en Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Obtenga más información sobre la configuración segura de forma predeterminada en Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 957ca3b563d4f1466dd537c3ae974a4fd61aa6f2
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346321"
---
# <a name="secure-by-default-in-office-365"></a>Proteger de forma predeterminada en Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"Seguro de forma predeterminada" es un término que se usa para definir la configuración predeterminada más segura posible.

Sin embargo, la seguridad debe equilibrarse con la productividad. Esto puede incluir el equilibrio entre:

- **Facilidad de** uso: Configuración no debe inquiete a la productividad del usuario.
- **Riesgo:** la seguridad puede bloquear actividades importantes.
- **Configuración heredada:** es posible que algunas configuraciones de productos y características anteriores deban mantenerse por motivos empresariales, incluso si se mejoran las configuraciones nuevas y modernas.

Microsoft 365 organizaciones con buzones en Exchange Online están protegidas por Exchange Online Protection (EOP). Esta protección incluye:

- El correo electrónico con malware sospechoso se pondrá automáticamente en cuarentena y se notificará a los destinatarios. Consulte [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).
- El correo electrónico identificado como phishing de elevada confianza se controlará de acuerdo con la acción de directiva contra correo no deseado. Vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

Para obtener más información acerca de EOP, [vea Exchange Online Protection overview](exchange-online-protection-overview.md).

Dado que Microsoft quiere mantener a nuestros clientes seguros de forma predeterminada, algunas invalidaciones de inquilinos no se aplican para malware o phishing de elevada confianza. Estas invalidaciones incluyen:

- Listas de remitentes permitidos o listas de dominios permitidos (directivas contra correo no deseado)
- Outlook Caja fuerte remitentes
- Lista de direcciones IP permitidos (filtrado de conexiones)

Encontrará más información sobre estas invalidaciones en [Crear listas de remitentes seguros.](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> Estamos en el proceso de desaprovechar la acción Mover mensaje a carpeta de correo no deseado para un veredicto de correo electrónico de **suplantación** de identidad de confianza alta en las directivas contra correo no deseado de EOP.  Las directivas contra correo no deseado que usan esta acción para mensajes de suplantación de identidad de elevada confianza se convertirán en **mensaje en cuarentena.** La **acción Redirigir mensaje a dirección de correo** electrónico para mensajes de suplantación de identidad de elevada confianza no se ha afectado.

Proteger de forma predeterminada no es una configuración que se puede desactivar o desactivar, pero es la forma en que nuestro filtrado funciona de forma predeterminada para mantener mensajes potencialmente peligrosos o no deseados fuera de los buzones. El malware y los mensajes de phishing de elevada confianza deben estar en cuarentena. Solo los administradores pueden administrar mensajes que se ponen en cuarentena como malware o phishing de elevada confianza, y también pueden notificar falsos positivos a Microsoft desde allí. Para obtener más información, vea [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Más información sobre por qué estamos haciendo esto

El ánimo de ser seguro de forma predeterminada es: estamos tomando la misma acción en el mensaje que realizaría si conociera el mensaje malintencionado, incluso cuando una excepción configurada de otro modo permitiría la entrega del mensaje. Este es el mismo enfoque que siempre hemos usado en malware y ahora estamos extendiendo este mismo comportamiento a mensajes de suplantación de identidad de elevada confianza.

Nuestros datos indican que un usuario tiene 30 veces más probabilidades de hacer clic en un vínculo malintencionado en los mensajes de la carpeta Correo no deseado frente a cuarentena. Nuestros datos también indican que la tasa de falsos positivos (mensajes buenos marcados como negativos) para mensajes de suplantación de identidad de elevada confianza es muy baja y los administradores pueden resolver los falsos positivos con envíos de administrador.

También determinamos que el remitente permitido y las listas de dominios permitidos en las directivas contra correo no deseado y los remitentes Caja fuerte en Outlook eran demasiado amplios y causaban más daños que buenos.

Para ponerlo de otra manera: como servicio de seguridad, estamos actuando en su nombre para evitar que los usuarios se pongan en peligro.

## <a name="exceptions"></a>Excepciones

> [!NOTE]
> En julio de 2021, la seguridad se extenderá de forma predeterminada a Exchange de flujo de correo (también conocidas como reglas de transporte). Si usa reglas de flujo de correo para permitir simulaciones de suplantación de identidad de terceros o entrega [](configure-advanced-delivery.md) sin filtrar a buzones de operación de seguridad, finalmente deberá eliminar estas reglas y cambiar al uso de la directiva de entrega avanzada cuando la característica esté _disponible._

La única invalidación que permite que los mensajes de suplantación de identidad de elevada confianza omita el filtrado son las reglas de flujo de correo. Para usar reglas de flujo de correo para omitir el filtrado, vea Usar reglas de flujo de [correo para establecer el SCL en mensajes](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Solo debe considerar el uso de invalidaciones en los siguientes escenarios:

- Simulaciones de phishing: los ataques simulados pueden ayudarle a identificar usuarios vulnerables antes de que un ataque real impacte en su organización.
- Buzones de seguridad/SecOps: buzones dedicados usados por los equipos de seguridad para obtener mensajes sin filtrar (tanto buenos como malos). Teams revisar para ver si contienen contenido malintencionado.
- Filtros de terceros: la seguridad de forma predeterminada no se aplica cuando el registro MX del dominio no apunta a Office 365.
- Falsos positivos: es posible que quieras permitir temporalmente determinados mensajes que Microsoft sigue analizando a través de [envíos de administrador.](admin-submission.md) Al igual que con todas las invalidaciones, se recomienda que sean temporales.
