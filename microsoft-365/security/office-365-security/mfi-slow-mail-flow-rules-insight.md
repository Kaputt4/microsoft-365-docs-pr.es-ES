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
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información Corregir reglas de flujo de correo lento en el Centro de cumplimiento de seguridad & para identificar y corregir reglas de flujo de correo ineficaces o interrumpidas (también conocidas como reglas de transporte) en su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 650389529f2a5d811f71b7c3f755d93e7e734d81
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65128748"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Corrección de la información de reglas de flujo de correo lento en el Centro de cumplimiento de seguridad &

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Las reglas de flujo de correo ineficaces (también conocidas como reglas de transporte) pueden provocar retrasos en el flujo de correo para su organización. Esta información informa de las reglas de flujo de correo que afectan al flujo de correo de la organización. Algunos ejemplos de estos tipos de reglas son:

- Condiciones que usan **Es miembro de** para grupos grandes.
- Condiciones que usan la coincidencia de patrones de expresiones regulares complejas (regex).
- Condiciones que usan la comprobación de contenido en los datos adjuntos.

La información **corregir reglas de flujo de correo lento** en el área **Recomendado para usted** del [panel Flujo de correo](mail-flow-insights-v2.md) del [Centro de cumplimiento de seguridad &](https://protection.office.com) le notifica cuando una regla de flujo de correo tarda demasiado tiempo en completarse.

Esta información aparece solo después de detectar la condición (si no tiene ningún bucle de correo, no verá la información).

Puede usar esta notificación para ayudarle a identificar y ajustar las reglas de flujo de correo para ayudar a reducir los retrasos en el flujo de correo.

:::image type="content" source="../../media/mfi-fix-slow-mail-flow-rules.png" alt-text="Información sobre la corrección de reglas de flujo de correo lento en el área Recomendado para usted del panel Flujo de correo" lightbox="../../media/mfi-fix-slow-mail-flow-rules.png":::

Al hacer clic en **Ver detalles** en el widget, aparece un control flotante con más información:

- **Regla**: puede mantener el puntero sobre el resumen para ver todas las condiciones, excepciones y acciones de la regla. Puede hacer clic en el resumen para editar la regla en el Centro de administración de Exchange (EAC) en <https://admin.exchange.microsoft.com/#/transportrules>.
- **Número de mensajes evaluados**: puede hacer clic en **Ver mensajes de ejemplo** para ver los resultados del [seguimiento](message-trace-scc.md) de mensajes de un ejemplo de los mensajes afectados por la regla.
- **Promedio de tiempo invertido en cada mensaje**
- **Mediana de tiempo invertido en un mensaje**: el valor intermedio que separa la mitad superior de los datos de la mitad inferior del tiempo.

:::image type="content" source="../../media/mfi-fix-slow-mail-flow-rules-details.png" alt-text="El control flotante Detalles que aparece después de hacer clic en Ver detalles en la información Corregir reglas de flujo de correo lento" lightbox="../../media/mfi-fix-slow-mail-flow-rules-details.png":::

Para obtener más información sobre las condiciones y excepciones en las reglas de flujo de correo, vea [Condiciones y excepciones de reglas de flujo de correo (predicados) en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="see-also"></a>Consulte también

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
