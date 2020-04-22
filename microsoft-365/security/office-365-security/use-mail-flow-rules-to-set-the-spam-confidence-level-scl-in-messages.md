---
title: Usar reglas de flujo de correo para el SCL en los mensajes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo establecer el SCL de los mensajes en Exchange Online Protection.
ms.openlocfilehash: cc75130d1e30b4cd64c32b1729c8145ad3088742
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636433"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>Usar reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL)

Si es un cliente de Microsoft 365 con buzones en Exchange online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP usa directivas contra correo no deseado (también conocidas como directivas de filtro de correo no deseado o directivas de filtro de contenido) para analizar los mensajes entrantes en busca de correo no deseado. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).

Si desea marcar determinados mensajes como correo no deseado antes de que se analicen mediante el filtrado de correo no deseado o marcar mensajes para que omitan el filtrado de correo no deseado, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para identificar los mensajes y establecer el nivel de confianza contra correo no deseado (SCL). Para obtener más información sobre el SCL, vea [nivel de confianza contra correo no deseado (SCL) en Office 365](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe tener asignados permisos en Exchange Online para poder realizar estos procedimientos. En concreto, debe tener asignado el rol **reglas de transporte** , que se asigna a las **funciones administración**de la organización, **Administración del cumplimiento**y administración de **registros** de forma predeterminada. Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Para abrir el EAC en Exchange Online, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Para obtener más información acerca de las reglas de flujo de correo en Exchange Online, consulte [reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) .

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Usar el EAC para crear una regla de flujo de correo que establezca el SCL de un mensaje

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

2. Haga **Add** ![clic en agregar](../../media/ITPro-EAC-AddIcon.png) icono Agregar y, a continuación, seleccione **crear una nueva regla**.

3. En la ventana **Nueva regla** que se abre, configure las siguientes opciones:

   - **Name**: escriba un nombre único y descriptivo para la regla.

   - Haga clic en **Más opciones**.

   - **Aplicar esta regla si**: Seleccione una o más condiciones para identificar los mensajes. Para obtener más información, consulte [mail Flow Rule conditions and Exceptions (Predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Haga lo siguiente**: seleccione **modificar las propiedades** \> del mensaje **establecer el nivel de confianza contra correo no deseado (SCL)**. En el cuadro de diálogo **especificar SCL** que aparece, configure uno de los siguientes valores:

   - **Omitir el filtrado de correo no deseado**: establece el SCL en-1, lo que significa que los mensajes omitirán el filtrado de correo no deseado.

     > [!CAUTION]
     > Tenga cuidado con la autorización de mensajes para omitir el filtrado de correo no deseado. Los atacantes pueden usar esta vulnerabilidad para enviar mensajes de suplantación de identidad (phishing) y otros mensajes malintencionados a la organización. Las reglas de flujo de correo requieren más que solo la dirección de correo electrónico o el dominio del remitente. Para obtener más información, vea [crear listas de remitentes seguros en Office 365](create-safe-sender-lists-in-office-365.md).

   - de **0 a 4**: el mensaje se envía a través del filtrado de correo no deseado para su procesamiento adicional.

   - **5 o 6**: el mensaje se marca como **correo no deseado**. La acción que ha configurado para los veredictos de filtrado de **correo no deseado** en las directivas contra correo no deseado se aplica al mensaje (el valor predeterminado es **mover mensaje a la carpeta de correo electrónico no deseado**).

   - de **7 a 9**: el mensaje se marca como **correo no deseado de confianza alta**. La acción que ha configurado para los veredictos de filtrado de **correo no deseado de confianza alta** en las directivas contra correo no deseado se aplica al mensaje (el valor predeterminado es **mover mensaje a la carpeta correo electrónico no deseado**).

4. Especifique las propiedades adicionales que desee para la regla. Cuando haya terminado, haga clic en **Guardar**.

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que este procedimiento funciona correctamente, envíe un mensaje de correo electrónico a una persona de su organización y compruebe que la acción que se realiza en el mensaje sea como se esperaba. Por ejemplo, si **establece el nivel de confianza de correo no deseado (SCL)** en **Omitir el filtrado de correo no deseado**, el mensaje debe enviarse a la bandeja de entrada del destinatario especificado. Sin embargo, si **establece el nivel de confianza de correo no deseado (SCL)** en **9** y la acción **Correo no deseado de confianza alta** para las directivas de filtro de contenido aplicables es mover el mensaje a la carpeta de correo no deseado, el mensaje debe enviarse a la carpeta de correo no deseado del destinatario especificado.
