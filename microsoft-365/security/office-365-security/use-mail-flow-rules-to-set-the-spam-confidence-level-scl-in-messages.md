---
title: Usar reglas de flujo de correo al SCL en mensajes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo crear reglas de flujo de correo (reglas de transporte) para identificar mensajes y establecer el nivel de confianza de correo no deseado (SCL) de los mensajes en Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 795347046342ea17870e7758a6327facf51315a4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206091"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Usar reglas de flujo de correo para establecer el nivel de confianza de correo no deseado (SCL) en los mensajes de EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP usa directivas contra correo no deseado (también conocidas como directivas de filtro de correo no deseado o directivas de filtro de contenido) para examinar los mensajes entrantes en busca de correo no deseado. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

Si desea marcar mensajes específicos como correo no deseado antes de que incluso los mida el filtrado de correo no deseado o marcar los mensajes para omitir el filtrado de correo no deseado, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para identificar los mensajes y establecer el nivel de confianza de correo no deseado (SCL). Para obtener más información acerca de SCL, vea Nivel de confianza de [correo no deseado (SCL) en EOP](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe tener asignados permisos en Exchange Online o Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo. En concreto, necesita el rol **Reglas** de transporte, que se asigna a los grupos de roles **Administración** de la **organización,** Administración de cumplimiento (administradores globales) y Administración **de** registros de forma predeterminada.

  Para obtener más información, consulte los siguientes temas:

  - [Permisos de Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Permisos en EOP independiente](feature-permissions-in-eop.md)
  - [Usar el EAC modificar la lista de miembros en grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para abrir el EAC en Exchange Online, vea [Centro de administración de Exchange en Exchange Online](/Exchange/exchange-admin-center). Para abrir el EAC en EOP independiente, vea Centro de [administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para obtener más información acerca de las reglas de flujo de correo en Exchange Online y Exchange Online Protection, vea Reglas de flujo de correo (reglas de [transporte) en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Usar el EAC para crear una regla de flujo de correo que establece el SCL de un mensaje

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

2. Haga **clic en** Agregar icono Agregar ![ ](../../media/ITPro-EAC-AddIcon.png) **y, a continuación, seleccione Crear una nueva regla.**

3. En la ventana **Nueva regla** que se abre, configure las siguientes opciones:

   - **Nombre:** escriba un nombre descriptivo único para la regla.

   - Haga clic en **Más opciones**.

   - **Aplique esta regla si**: seleccione una o más condiciones para identificar mensajes. Para obtener más información, vea Condiciones y excepciones de reglas de flujo de [correo (predicados) en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Haga lo siguiente:** Seleccione **Modificar las propiedades del mensaje** para establecer el nivel de confianza de correo no deseado \> **(SCL).** En el cuadro de diálogo Especificar **SCL** que aparece, configure uno de los siguientes valores:

   - **Omitir el filtrado de correo** no deseado: los mensajes omitirán el filtrado de correo no deseado.

     > [!CAUTION]
     > Tenga mucho cuidado al permitir que los mensajes omitan el filtrado de correo no deseado. Los atacantes pueden usar esta vulnerabilidad para enviar phishing y otros mensajes malintencionados a su organización. Las reglas de flujo de correo requieren algo más que la dirección de correo electrónico o el dominio del remitente. Para obtener más información, vea [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).

   - **De 0 a 4:** el mensaje se envía a través del filtrado de correo no deseado para un procesamiento adicional.

   - **5 o 6:** el mensaje se marca como **Correo no deseado**. La acción que configuró  para los veredictos de filtrado de correo no deseado en las directivas contra correo no deseado se aplica al mensaje (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**).

   - **7 a 9:** el mensaje se marca como correo no **deseado de confianza alta.** La acción que ha configurado para los veredictos de filtrado de **correo** no deseado de elevada confianza en las directivas contra correo no deseado se aplica al mensaje (el valor predeterminado es Mover mensaje a la carpeta correo **no deseado**).

4. Especifique las propiedades adicionales que desee para la regla. Cuando haya terminado, haga clic en **Guardar**.

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que este procedimiento funciona correctamente, envíe un mensaje de correo electrónico a una persona de su organización y compruebe que la acción que se realiza en el mensaje sea como se esperaba. Por ejemplo, si **establece el nivel de confianza de correo no deseado (SCL)** en **Omitir el filtrado de correo no deseado**, el mensaje debe enviarse a la bandeja de entrada del destinatario especificado. Sin embargo, si establece el nivel de confianza de  correo no deseado **(SCL)** en **9** y la acción de correo no deseado de alta confianza para las directivas contra correo no deseado aplicables es mover el mensaje a la carpeta correo no deseado, el mensaje debe enviarse a la carpeta de correo no deseado del destinatario especificado.