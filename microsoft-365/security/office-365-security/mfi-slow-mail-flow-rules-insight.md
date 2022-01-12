---
title: Corrección de información de reglas de flujo de correo lento
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información corregir reglas de flujo de correo lento en el Centro de seguridad y cumplimiento de & para identificar y corregir reglas de flujo de correo ineficaces o rotas (también conocidas como reglas de transporte) en su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9866761e683e15d34d81b8ea0962d974b0b474da
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61935226"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Corregir la información de reglas de flujo de correo lento en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Las reglas de flujo de correo ineficaces (también conocidas como reglas de transporte) pueden provocar retrasos en el flujo de correo para su organización. Esta información informa de las reglas de flujo de correo que tienen un impacto en el flujo de correo de la organización. Algunos ejemplos de estos tipos de reglas son:

- Condiciones de las que **se usa Is member of** for large groups.
- Condiciones que usan coincidencias de patrones de expresión regular compleja (regex).
- Condiciones que usan la comprobación de contenido en datos adjuntos.

La información **corregir** reglas de  flujo de correo [](mail-flow-insights-v2.md) lento en el área Recomendado para usted del panel flujo de correo en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) le notifica cuándo una regla de flujo de correo tarda demasiado tiempo en completarse.

Esta información aparece solo después de que se detecte la condición (si no tiene bucles de correo, no verá la información).

Puede usar esta notificación para ayudarle a identificar y ajustar las reglas de flujo de correo para ayudar a reducir los retrasos en el flujo de correo.

![Corregir la información de reglas de flujo de correo lento en el área Recomendado para usted del panel flujo de correo.](../../media/mfi-fix-slow-mail-flow-rules.png)

Al hacer clic **en Ver detalles** en el widget, aparece un control flotante con más información:

- **Regla:** puede pasar el puntero sobre el resumen para ver todas las condiciones, excepciones y acciones de la regla. Puede hacer clic en el resumen para editar la regla en el Centro Exchange administración (EAC) en <https://admin.exchange.microsoft.com/#/transportrules> .
- **Número de mensajes evaluados:** puede hacer clic [](message-trace-scc.md) en Ver mensajes de ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes que se vieron afectados por la regla. 
- **Tiempo promedio invertido en cada mensaje**
- **Mediana de tiempo invertido en un mensaje:** el valor intermedio que separa la mitad superior de los datos de la mitad inferior del tiempo.

![Control desplegable de detalles que aparece después de hacer clic en Ver detalles en la información sobre las reglas de flujo de correo lento fix.](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Para obtener más información acerca de las condiciones y excepciones en las reglas de flujo de correo, vea Condiciones de regla de flujo de correo y excepciones [(predicados) en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="see-also"></a>Vea también

Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).