---
title: Revisión de administrador para mensajes notificados
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Aprende a revisar los mensajes que se notifican y a enviar comentarios a los usuarios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 619cd35b6a60f0d50aa6c13e4cad2b8d7ae947a8
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730981"
---
# <a name="admin-review-for-reported-messages"></a>Revisión de administrador para mensajes notificados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> La información de este artículo se refiere a un producto de vista previa que puede modificarse considerablemente antes de su lanzamiento comercial. Este documento se proporciona únicamente con fines de evaluación y exploración.

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 con Exchange Online buzones de correo y Microsoft Defender para Office 365, los administradores ahora pueden enviar mensajes con plantilla de vuelta a los usuarios finales después de revisar los mensajes notificados. Esto se puede personalizar para su organización y también en función del veredicto del administrador.

Esta característica está diseñada para enviar comentarios a los usuarios, pero no cambia los veredictos de los mensajes en el sistema. Para ayudar a Microsoft a actualizar y mejorar sus filtros, deberá enviar mensajes para su análisis mediante [el envío de administrador.](admin-submission.md)

Solo podrá marcar y notificar a los usuarios los resultados de la revisión si el mensaje se notificó como [falsos positivos o falsos negativos](report-false-positives-and-false-negatives.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para modificar la configuración de envíos de usuarios, debe ser miembro de uno de los siguientes grupos de roles:
    - Administración de la organización o Administrador de seguridad en [el Centro de seguridad](permissions-microsoft-365-compliance-security.md).
    - Administración de la [organización en Exchange Online](/Exchange/permissions-exo/permissions-exo).

- También necesitarás acceso a la Exchange Online PowerShell. Si la cuenta que está intentando usar no tiene acceso Exchange Online PowerShell, recibirá un error que indica Especificar una dirección de correo electrónico en *su dominio*. Para obtener más información acerca de cómo habilitar o deshabilitar el acceso a Exchange Online PowerShell, consulte los siguientes temas:
    - [Habilitar o deshabilitar el acceso a Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)
    - [Reglas de acceso de cliente en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>Configurar los mensajes usados para notificar a los usuarios

1. En el [centro Microsoft 365 seguridad,](../defender/overview-security-center.md)vaya a **Directivas &** Directivas de amenazas Configuración del \>  \> **mensaje notificado por el usuario.**

2. Si desea especificar el nombre para mostrar del remitente **Office 365,** active la casilla especificar una dirección de correo electrónico para usarla como remitente en la sección Notificaciones de correo electrónico para los **resultados** de la revisión de administrador y escriba el nombre que desea usar. Esta es la dirección de correo electrónico que estará visible en Outlook y a la que se dirigirán las respuestas.

3. Si desea personalizar cualquiera de las plantillas, haga clic **en Personalizar notificación de correo electrónico.** En este menú desplegable, solo podrá personalizar lo siguiente:
    - Suplantación de identidad (phishing)
    - Correo no deseado
    - No se encontraron amenazas
    - Formación de sensibilización
    - Pie de página

4. Cuando haya terminado, haga clic en **Guardar**. Para borrar estos valores, haga clic en **Descartar** en la página Envíos de usuario.
