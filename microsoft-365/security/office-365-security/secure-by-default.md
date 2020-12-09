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
ms.openlocfilehash: 758d2169d80630a38c0b498e8c1848568e5ec941
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602046"
---
# <a name="secure-by-default-in-office-365"></a>Seguro de forma predeterminada en Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Seguro de forma predeterminada" es un término que se usa para definir los valores predeterminados más seguros posible.

Sin embargo, la seguridad debe estar equilibrada con la productividad. Esto puede incluir un equilibrio entre:

- **Facilidad de uso**: la configuración no debe obtener la productividad de los usuarios.
- **Riesgo**: la seguridad puede bloquear actividades importantes.
- **Configuración heredada**: es posible que algunas configuraciones de productos y características anteriores deban mantenerse por motivos empresariales, incluso si se han mejorado las opciones nuevas y modernas.

Microsoft 365 organizaciones con buzones de correo en Exchange online están protegidas por Exchange Online Protection (EOP). Esta protección incluye:

- El correo electrónico con el malware sospechoso se pondrá en cuarentena automáticamente y se notificará a los destinatarios. Vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).
- El correo electrónico identificado como una identidad de confianza alta se controlará de acuerdo con la acción de la Directiva contra correo no deseado. Consulte [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

Para obtener más información acerca de EOP, consulte [Exchange Online Protection Overview](exchange-online-protection-overview.md).

Debido a que Microsoft desea mantener a nuestros clientes seguros de forma predeterminada, algunos invalidaciones de los inquilinos no se aplican para el malware o la suplantación de identidad de confianza alta. Estas invalidaciones incluyen:

- Listas de remitentes permitidos o listas de dominios permitidos (directivas contra correo no deseado)
- Remitentes seguros de Outlook
- Lista de direcciones IP permitidas (filtrado de la conexión)

Puede encontrar más información sobre estas invalidaciones en [crear listas de remitentes seguros](create-safe-sender-lists-in-office-365.md).

Seguro de forma predeterminada no es un valor que se puede activar o desactivar, pero es la forma en que nuestro filtrado se encuentra fuera del cuadro para conservar los mensajes potencialmente peligrosos o no deseados de los buzones. El malware y los mensajes de suplantación de identidad de alta confianza se deben poner en cuarentena. Solo los administradores pueden administrar mensajes que estén en cuarentena como malware o un phishing de confianza alta, y también pueden informar de falsos positivos a Microsoft desde allí. Para obtener más información, consulte [administrar mensajes en cuarentena y archivos como un administrador en EOP](manage-quarantined-messages-and-files.md) .

## <a name="more-on-why-were-doing-this"></a>Más información sobre por qué estamos haciendo esto

El espíritu de seguro de forma predeterminada es: estamos llevando a cabo la misma acción en el mensaje que haría si conociera el mensaje malintencionado, incluso si había un permiso permitido. Se trata del mismo enfoque que hemos usado en malware y ahora estamos ampliando este mismo comportamiento a los mensajes de suplantación de identidad de alta confianza. Nuestros datos indican que la tasa de falsos positivos para los mensajes de suplantación de identidad de alta confianza es muy baja y los administradores pueden resolver cualquier falso positivo con envíos de administración. Nuestros datos también indican que las listas de remitentes permitidos y las listas de dominios permitidos en las directivas contra correo no deseado y los remitentes seguros de Outlook son demasiado amplias y que causan un mayor daño.

Para agregarla de otra forma: como un servicio de seguridad, estamos actuando en su nombre para evitar que los usuarios se vean comprometidos. Además, seguro de forma predeterminada no es una adquisición completa de las opciones disponibles para los mensajes de suplantación de identidad de alta confianza en las directivas contra correo no deseado. Aunque recomendamos la cuarentena, las otras acciones que están siempre disponibles están todavía disponibles (mover a la carpeta de correo no deseado o redirigirla a una dirección de correo electrónico).

## <a name="exceptions"></a>Exceptions

El único reemplazo que permite un mensaje de suplantación de identidad de alta confianza para omitir el filtrado son las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte). Para usar reglas de flujo de correo para omitir el filtrado, consulte [usar reglas de flujo de correo para establecer el SCL en los mensajes](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Solo debe considerar la posibilidad de usar reemplazos en los siguientes escenarios:

- Simulaciones de suplantación de identidad (phishing): los ataques simulados pueden ayudar a identificar los usuarios vulnerables antes de que un ataque real afecte a su organización.
- Buzones de seguridad/SecOps: buzones dedicados usados por los equipos de seguridad para obtener mensajes no filtrados (buenos y no válidos). Los equipos pueden revisar para ver si contienen contenido malintencionado.
- Filtros de terceros: algunos proveedores de terceros recomendarán que se desactive EOP (SCL =-1), ya que el filtro de terceros administrará el filtrado de correo. Microsoft no recomienda desactivar EOP como EOP es necesario para [Microsoft defender para Office 365](office-365-atp.md). En su lugar, la recomendación es activar el [filtrado mejorado para los conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
- Falsos positivos: es posible que desee permitir temporalmente determinados mensajes que Microsoft todavía está analizando [a través de los envíos de administración](admin-submission.md). Como con todas las invalidaciones, se recomienda que sean temporales.
