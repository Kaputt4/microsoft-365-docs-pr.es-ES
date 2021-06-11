---
title: Configurar la entrega de simulaciones de suplantación de identidad de terceros a usuarios y mensajes sin filtrar a buzones de SecOps
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
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Los administradores pueden aprender a usar la directiva de entrega avanzada en Exchange Online Protection (EOP) para identificar mensajes que no deben filtrarse en escenarios compatibles específicos (simulaciones de suplantación de identidad de terceros y mensajes entregados a buzones de operaciones de seguridad (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: deaad11b6397cd53017c0972a624b67a9623887f
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879113"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Configurar la entrega de simulaciones de suplantación de identidad de terceros a usuarios y mensajes sin filtrar a buzones de SecOps

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> La característica que se describe en este artículo está en Versión preliminar, no está disponible para todos y está sujeta a cambios.

Para mantener la organización segura de forma [predeterminada,](secure-by-default.md)Exchange Online Protection (EOP) no permite listas seguras ni omitir el filtrado de mensajes identificados como malware o phishing de elevada confianza. Sin embargo, hay escenarios específicos que requieren la entrega de mensajes sin filtrar. Por ejemplo:

- **Simulaciones de suplantación** de identidad de terceros: los ataques simulados pueden ayudarle a identificar usuarios vulnerables antes de que un ataque real impacte en su organización.
- Buzones de operaciones de seguridad **(SecOps):** buzones dedicados que usan los equipos de seguridad para recopilar y analizar mensajes sin filtrar (tanto buenos como malos).

Use la directiva _de entrega avanzada_ en Microsoft 365 para evitar que estos mensajes en estos _escenarios específicos_ se filtren. <sup>\*</sup> La directiva de entrega avanzada garantiza que los mensajes en estos escenarios consigan los siguientes resultados:

- Los filtros de EOP y Microsoft Defender Office 365 realizar ninguna acción en estos mensajes.<sup>\*</sup>
- [La purga de hora cero (ZAP)](zero-hour-auto-purge.md) para correo no deseado y suplantación de identidad (phishing) no toma ninguna acción en estos mensajes.<sup>\*</sup>
- [Las alertas predeterminadas](alerts.md) del sistema no se desencadenan para estos escenarios.
- [AIR y la agrupación en clústeres en Defender para Office 365](office-365-air.md) omite estos mensajes.
- Específicamente para simulaciones de suplantación de identidad de terceros:
  - [Los envíos de](admin-submission.md) administrador generan una respuesta automática que indica que el mensaje forma parte de una campaña de simulación de suplantación de identidad (phishing) y no es una amenaza real. Las alertas y AIR no se desencadenarán.
  - [Caja fuerte vínculos en Defender para Office 365](safe-links.md) no bloquea ni detona las direcciones URL identificadas específicamente en estos mensajes.
  - [Caja fuerte datos adjuntos en Defender para Office 365](safe-attachments.md) no detonan datos adjuntos en estos mensajes.

<sup>\*</sup> No puede omitir el filtrado de malware o ZAP para malware.

Los mensajes identificados por la directiva de entrega avanzada no son amenazas de seguridad, por lo que los mensajes se marcan como invalidaciones del sistema. Los administradores pueden filtrar y analizar estas invalidaciones del sistema en las siguientes experiencias:

- [Explorador de amenazas/detecciones en tiempo real en Defender para Office 365 plan 2](threat-explorer.md)
- La [entidad Email Page en el Explorador de amenazas/Detecciones en tiempo real](mdo-email-entity-page.md)
- Informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Búsqueda avanzada en Microsoft Defender para endpoint](../defender-endpoint/advanced-hunting-overview.md)
- [Vistas de campañas](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Abra el portal Microsoft 365 Defender en <https://security.microsoft.com> . Para ir directamente a la **página Entrega avanzada,** abra <https://security.microsoft.com/advanceddelivery> .

- Debe tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:
  - Para crear, modificar o quitar la configuración de la directiva de  entrega avanzada, debe ser miembro del grupo de  roles Administrador de seguridad en el portal de **Microsoft 365 Defender** y miembro del grupo de roles Administración de la organización en **Exchange Online**.  
  - Para obtener acceso de solo lectura a la directiva de entrega avanzada, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.

  Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > Agregar usuarios al rol Azure Active Directory correspondiente proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Usar el portal Microsoft 365 Defender para configurar buzones de SecOps en la directiva de entrega avanzada

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de \> **colaboración** & \> **reglas de** amenazas Sección Reglas de entrega \>  \> **avanzada**.

2. En la **página Entrega avanzada,** compruebe que la pestaña buzón **de SecOps** está seleccionada y, a continuación, siga uno de los pasos siguientes:
   - Haga ![ clic en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar**.
   - Si no hay simulaciones de suplantación de identidad configuradas, haga clic en **Agregar**.

3. En el control desplegable Editar buzones de SecOps que se abre, escriba un buzón de Exchange Online existente que desee designar como buzón de **SecOps** siguiendo uno de los pasos siguientes:
   - Haga clic en el cuadro, deje que se resuelva la lista de buzones y, a continuación, seleccione el buzón.
   - Haga clic en el cuadro para empezar a escribir un identificador para el buzón (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de cuenta, etc.) y seleccione el buzón (nombre para mostrar) de los resultados.

     Repita este paso tantas veces como sea necesario. Los grupos de distribución no están permitidos.

     Para quitar un valor existente, haga clic en Quitar ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

4. Cuando haya terminado, haga clic en **Guardar**.

Las entradas de buzón de SecOps que configuró se muestran en la **pestaña Buzón de SecOps.** Para realizar cambios, haga clic ![ en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar** en la pestaña.

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Use el portal Microsoft 365 Defender para configurar simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de \> **colaboración** & \> **reglas de** amenazas Sección Reglas de entrega \>  \> **avanzada**.

2. En la **página Entrega avanzada,** seleccione la pestaña **Simulación de suplantación** de identidad y, a continuación, realice uno de los siguientes pasos:
   - Haga ![ clic en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar**.
   - Si no hay simulaciones de suplantación de identidad configuradas, haga clic en **Agregar**.

3. En el **control desplegable Editar simulación de suplantación** de identidad de terceros que se abre, configure las siguientes opciones:

   - **Dominio** de envío: expanda esta configuración y escriba al menos un dominio de dirección de correo electrónico (por ejemplo, contoso.com) haciendo clic en el cuadro, especificando un valor y presionando Entrar o seleccionando el valor que se muestra debajo del cuadro. Repita este paso tantas veces como sea necesario. Puede agregar hasta 10 entradas.
   - **Enviar IP:** expanda esta configuración y escriba al menos una dirección IPv4 válida haciendo clic en el cuadro, especificando un valor y presionando Entrar o seleccionando el valor que se muestra debajo del cuadro. Repita este paso tantas veces como sea necesario. Puede agregar hasta 10 entradas. Los valores admitidos son:
     - IP única: por ejemplo, 192.168.1.1.
     - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.
     - IP cidr: por ejemplo, 192.168.0.1/25.
   - Direcciones **URL** de simulación para permitir: expanda esta configuración y, opcionalmente, escriba direcciones URL específicas que forman parte de la campaña de simulación de suplantación de identidad que no se deben bloquear ni detonar haciendo clic en el cuadro, especificando un valor y presionando Entrar o seleccionando el valor que se muestra debajo del cuadro. Puede agregar hasta 10 entradas.

   Para quitar un valor existente, haga clic en Quitar ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

4. Cuando haya terminado, siga uno de los pasos siguientes:
   - **Primera vez:** haga clic **en Agregar** y, a continuación, en **Cerrar**.
   - **Editar existente:** haga clic **en Guardar** y, a continuación, en **Cerrar**.

Las entradas de simulación de suplantación de identidad de terceros que configuró se muestran en la pestaña **Simulación de suplantación de** identidad. Para realizar cambios, haga clic ![ en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar** en la pestaña.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Escenarios adicionales que requieren la omisión de filtrado

Además de los dos escenarios con los que la directiva de entrega avanzada puede ayudarle, hay otros escenarios que pueden requerir omitir el filtrado:

- **Filtros de terceros:** si el registro  MX de su dominio no apunta a Office 365 (los mensajes se enruta en otro lugar primero), [la](secure-by-default.md) seguridad de forma predeterminada no *está disponible*.

  Para omitir el filtrado de Microsoft para los mensajes que ya han sido evaluados por el filtrado de terceros, use reglas de flujo de correo (también conocidas como reglas de transporte). Para obtener más información, vea [Usar reglas de flujo de correo para establecer el SCL en mensajes](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).

- **Falsos positivos** en revisión: es posible que desee permitir temporalmente que determinados mensajes que Microsoft sigue analizando a través de [envíos](admin-submission.md) de administrador informen de mensajes buenos conocidos que se marcan incorrectamente como incorrectos para Microsoft (falsos positivos). Al igual que con todas las invalidaciones, se **_recomienda encarecidamente_** que estas asignaciones sean temporales.
