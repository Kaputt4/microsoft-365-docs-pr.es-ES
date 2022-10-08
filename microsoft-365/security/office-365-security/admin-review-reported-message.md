---
title: Revisión del administrador para los mensajes de los que se informe
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
ms.collection:
- m365-security
ms.custom: ''
description: Obtenga información sobre cómo revisar los mensajes que se notifican y enviar comentarios a los usuarios.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 4fbb592512eb9bc872a5c721f48e43ec5ad25a2a
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68066836"
---
# <a name="admin-review-for-reported-messages"></a>Revisión del administrador para los mensajes de los que se informe

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de Exchange Online y Microsoft Defender para Office 365, los administradores ahora pueden enviar mensajes con plantilla de vuelta a los usuarios finales después de revisar los mensajes notificados. Las plantillas se pueden personalizar para su organización y también en función del veredicto del administrador.

La característica está diseñada para enviar comentarios a los usuarios, pero no cambia los veredictos de los mensajes en el sistema. Para ayudar a Microsoft a actualizar y mejorar sus filtros, debe enviar mensajes para su análisis mediante [Administración envío](admin-submission.md).

Solo podrá marcar y notificar a los usuarios los resultados de la revisión si el mensaje se ha notificado como [falsos positivos o falsos negativos](report-false-positives-and-false-negatives.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

- Para modificar la configuración de los envíos de usuarios, debe ser miembro de uno de los siguientes grupos de roles:
  - Administración de la organización o administrador de seguridad en el [portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).
  - Administración de la organización en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- También necesitará acceso a Exchange Online PowerShell. Si la cuenta que intenta usar no tiene acceso a Exchange Online PowerShell, recibirá un error que indica *Especificar una dirección de correo electrónico en el dominio*. Para obtener más información sobre cómo habilitar o deshabilitar el acceso a Exchange Online PowerShell, consulte los temas siguientes:
  - [Habilitar o deshabilitar el acceso al PowerShell de Exchange Online](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Reglas de acceso de cliente en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="notify-users-from-within-the-portal"></a>Notificar a los usuarios desde el portal

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en Email & **envíos de** **colaboración**\>. Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. Haga clic en **Mensajes notificados** por el usuario y, a continuación, seleccione el mensaje que desea marcar y notificar.

3. Seleccione la lista desplegable **Marcar como y notificar** y, a continuación, seleccione **No se encontraron amenazas**, **Phishing** o **Correo no deseado**.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/admin-review-send-message-from-portal.png" alt-text="Página que muestra los mensajes notificados por el usuario" lightbox="../../media/admin-review-send-message-from-portal.png":::

El mensaje notificado se marcará como falso positivo o falso negativo, y se enviará automáticamente un correo electrónico desde el portal notificando al usuario que ha notificado el mensaje.

## <a name="customize-the-messages-used-to-notify-users"></a>Personalización de los mensajes usados para notificar a los usuarios

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos de usuarios en Email & Directivas** de **colaboración** \> **& Reglas** \> **Directivas de amenazas** \> **Configuración de mensajes notificados por el usuario** en la sección **Otros**. Para ir directamente a la página **Envíos de usuarios** , use <https://security.microsoft.com/userSubmissionsReportMessage>.

2. En la página **Envíos** de usuarios, si desea especificar el nombre para mostrar del remitente, active la casilla **Especificar Office 365 dirección de correo electrónico que se usará como remitente** en la sección **Email notificaciones para los resultados de la revisión del administrador** y escriba el nombre que desea usar. La dirección de correo electrónico que será visible en Outlook y todas las respuestas irán allí.

3. Si desea personalizar cualquiera de las plantillas, haga clic en **Personalizar notificación por correo electrónico** en la parte inferior de la página. En el control flotante que se abre, solo puede personalizar lo siguiente:

    - Suplantación de identidad (phishing)
    - Basura
    - No se encontraron amenazas
    - Pie de página

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/admin-review-customize-message.png" alt-text="Página Personalizar mensaje de confirmación" lightbox="../../media/admin-review-customize-message.png":::

4. Cuando haya terminado, haga clic en **Guardar**. Para borrar estos valores, haga clic en **Descartar** en la página **Envíos de usuarios** .
