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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Obtenga más información sobre la configuración segura de forma predeterminada en Exchange Online Protection (EOP)
ms.openlocfilehash: 8db8e7af569114e5829d24d65b8eee89c9dce8c3
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787978"
---
# <a name="secure-by-default-in-office-365"></a>Proteger de forma predeterminada en Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Seguro de forma predeterminada" es un término que se usa para definir la configuración predeterminada más segura posible.

Sin embargo, la seguridad debe equilibrarse con la productividad. Esto puede incluir el equilibrio entre:

- **Facilidad de** uso: la configuración no debe inquiete a la productividad del usuario.
- **Riesgo:** la seguridad puede bloquear actividades importantes.
- **Configuración heredada:** es posible que algunas configuraciones de productos y características anteriores deban mantenerse por motivos empresariales, incluso si se mejora la configuración nueva y moderna.

Las organizaciones de Microsoft 365 con buzones en Exchange Online están protegidas por Exchange Online Protection (EOP). Esta protección incluye:

- El correo electrónico con sospechoso de malware se pondrá automáticamente en cuarentena y se notificará a los destinatarios. Vea [Configurar directivas antimalware en EOP.](configure-anti-malware-policies.md)
- El correo electrónico identificado como suplantación de identidad de confianza alta se controlará de acuerdo con la acción de directiva contra correo no deseado. Vea [Configurar directivas contra correo no deseado en EOP.](configure-your-spam-filter-policies.md)

Para obtener más información acerca de EOP, vea [información general sobre Exchange Online Protection.](exchange-online-protection-overview.md)

Dado que Microsoft quiere mantener seguros nuestros clientes de forma predeterminada, algunos reemplazos de inquilinos no se aplican para malware o suplantación de identidad de confianza alta. Estos reemplazos incluyen:

- Listas de remitentes permitidos o listas de dominios permitidos (directivas contra correo no deseado)
- Remitentes seguros de Outlook
- Lista de direcciones IP permitidos (filtrado de conexiones)

Puede encontrar más información sobre estos reemplazos en [Crear listas de remitentes seguros.](create-safe-sender-lists-in-office-365.md)

De forma predeterminada, la seguridad no es una opción que se puede activado o desactivado, pero es la forma en que nuestro filtrado funciona de forma predeterminada para mantener mensajes potencialmente peligrosos o no deseados fuera de sus buzones. Los mensajes de suplantación de identidad (phishing) de malware y de confianza alta deben ponerse en cuarentena. Solo los administradores pueden administrar los mensajes que se ponen en cuarentena como malware o phishing de confianza alta, y también pueden notificar falsos positivos a Microsoft desde allí. Para obtener más información, vea Administrar mensajes y archivos en cuarentena [como administrador en EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Más información sobre por qué estamos haciendo esto

De manera predeterminada, la seguridad es: estamos llevando a cabo la misma acción en el mensaje que realizaría si supo que el mensaje era malintencionado, incluso si se hubiera permitido. Este es el mismo enfoque que hemos usado en el malware y ahora estamos ampliando este mismo comportamiento a los mensajes de suplantación de identidad de confianza alta. Nuestros datos indican que la tasa de falsos positivos para mensajes de suplantación de identidad de confianza alta es muy baja y los administradores pueden resolver los falsos positivos con envíos de administrador. Nuestros datos también indican que las listas de remitentes permitidos y las listas de dominios permitidos en las directivas contra correo no deseado y remitentes seguros en Outlook eran demasiado amplias y causaban más daños que buenos.

Dicho de otro modo: como servicio de seguridad, estamos actuando en su nombre para evitar que los usuarios se pongan en peligro. Además, la seguridad de forma predeterminada no es una toma completa de las opciones disponibles para los mensajes de suplantación de identidad de alta confianza en las directivas contra correo no deseado. Aunque se recomienda poner en cuarentena, las demás acciones que siempre han estado disponibles siguen estando disponibles (mover a la carpeta de correo no deseado o redirigir a una dirección de correo electrónico).

## <a name="exceptions"></a>Exceptions

El único reemplazo que permite que los mensajes de suplantación de identidad de alta confianza omitan el filtrado son las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte). Para usar reglas de flujo de correo para omitir el filtrado, vea Usar reglas de flujo de [correo para establecer el SCL en mensajes.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Solo debe considerar el uso de invalidaciones en los siguientes escenarios:

- Simulaciones de suplantación de identidad: los ataques simulados pueden ayudarle a identificar usuarios vulnerables antes de que un ataque real repercuta en su organización.
- Buzones de seguridad/SecOps: buzones dedicados usados por los equipos de seguridad para obtener mensajes sin filtrar (tanto buenos como no). Después, Teams puede revisar si contienen contenido malintencionado.
- Filtros de terceros: la seguridad de forma predeterminada no se aplica cuando el registro MX del dominio no apunta a Office 365.
- Falsos positivos: es posible que desee permitir temporalmente ciertos mensajes que Microsoft sigue analizando a través de [envíos de administración.](admin-submission.md) Al igual que con todas las invalidaciones, se recomienda que sean temporales.
