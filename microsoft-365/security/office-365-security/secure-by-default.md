---
title: Seguro de forma predeterminada en Office 365
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
description: Obtenga más información acerca de la configuración de seguridad de forma predeterminada en Exchange Online Protection (EOP)
ms.openlocfilehash: d4345134e98ae204f73dfb51a0abf5136590a24c
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126666"
---
# <a name="secure-by-default-in-office-365"></a>Seguro de forma predeterminada en Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Seguro de forma predeterminada" es un término que se usa para definir los valores predeterminados más seguros posible.

Sin embargo, la seguridad debe estar equilibrada con la productividad. Esto puede incluir un equilibrio entre:

- Facilidad de uso: la configuración no debe obtener la productividad de los usuarios.
- Riesgo: la seguridad puede bloquear actividades importantes.
- Configuración heredada: es posible que algunas configuraciones de productos y características anteriores deban mantenerse por motivos empresariales, incluso si se han mejorado las opciones nuevas y modernas.

Microsoft 365 organizaciones con buzones de correo en Exchange online están protegidas por Exchange Online Protection (EOP). Esta protección incluye:

1. El correo electrónico con el malware sospechoso se pondrá en cuarentena automáticamente y se notificará a los destinatarios. Vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).
1. El correo electrónico de suplantación de identidad identificado como "alta confianza" se controlará de acuerdo con la acción contra la Directiva contra correo no deseado. Consulte [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

Debido a que Microsoft desea mantener a nuestros clientes seguros de forma predeterminada, algunos invalidaciones de los inquilinos no se aplican a malware o phish de confianza alta. Estas invalidaciones incluyen:

- Listas de remitentes permitidos o listas de dominios permitidos (directivas contra correo no deseado)
- Remitentes seguros de Outlook
- Lista de direcciones IP permitidas (filtrado de la conexión)

Puede encontrar más información sobre estas invalidaciones en [crear listas de remitentes seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).

Seguro de forma predeterminada esta es una configuración que puede activarse o desactivarse, pero el modo en que nuestro filtrado funciona de forma predeterminada para conservar los mensajes potencialmente peligrosos o no deseados de los buzones. El malware y la suplantación de identidad de confianza alta deben enviarse a cuarentena. Solo los administradores pueden administrar mensajes que se pusieron en cuarentena como malware o una suplantación de identidad de confianza alta y también pueden informar de falsos positivos a Microsoft desde allí. Para obtener más información, consulte [administrar mensajes en cuarentena y archivos como un administrador en EOP](manage-quarantined-messages-and-files.md) .

## <a name="exceptions"></a>Exceptions

El único reemplazo que permite un mensaje de suplantación de identidad de alta confianza para omitir el filtrado son las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte). Para usar reglas de flujo de correo para omitir el filtrado, consulte [usar reglas de flujo de correo para establecer el SCL en los mensajes](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Las invalidaciones solo deben usarse para:

- Simulaciones de suplantación de identidad (phishing): los ataques simulados pueden ayudar a identificar los usuarios vulnerables antes de que un ataque real afecte a su organización.
- Buzones de seguridad/SecOps: buzones dedicados usados por los equipos de seguridad para obtener mensajes no filtrados (buenos y no válidos). Los equipos pueden revisar para ver si contienen contenido malintencionado.
- Filtros de terceros: algunos proveedores de terceros recomiendan desactivar EOP (SCL =-1), ya que el filtro de terceros administrará el filtrado de correo. Microsoft no recomienda desactivar EOP como EOP es necesario para defender para Office 365.
- Falsos positivos: es posible que desee permitir determinados mensajes que Microsoft todavía está analizando mediante los [envíos de administración](admin-submission.md). Como con todas las invalidaciones, se recomienda que sean temporales.
