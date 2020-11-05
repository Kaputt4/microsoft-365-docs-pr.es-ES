---
title: Corrección de información de reglas de flujo de correo lento
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre cómo usar la solución Fix Slow mail Flow rules Insight en el centro de seguridad & cumplimiento para identificar y corregir reglas de flujo de correo ineficientes o ineficientes (también conocidas como reglas de transporte) en su organización.
ms.openlocfilehash: f51c5a577fc6d9c52e35a5217cae4ae94c546c9d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920553"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Corrección de las reglas de flujo de correo lenta información del centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Las reglas de flujo de correo ineficiente (también conocidas como reglas de transporte) pueden llevar a retrasos en el flujo de correo de la organización. Esta visión informa de las reglas de flujo de correo que afectan al flujo de correo de su organización. Algunos ejemplos de estos tipos de reglas son:

- Condiciones que usan **son miembros de** grupos grandes.
- Condiciones que usan la coincidencia de patrón de expresiones regulares complejas (regex).
- Condiciones que usan la comprobación de contenido en datos adjuntos.

La opción para **corregir reglas de flujo de correo con lentitud** en el área **recomendada para** el [panel del flujo de correo](mail-flow-insights-v2.md) en el centro de [seguridad & cumplimiento](https://protection.office.com) le avisa cuando una regla de flujo de correo tarda mucho tiempo en completarse.

Esta información sólo aparece cuando se detecta la condición (si no tiene bucles de correo, no verá la información).

Puede usar esta notificación para ayudarle a identificar y ajustar las reglas de flujo de correo para ayudar a reducir los retrasos del flujo de correo.

![Corrección de la información lenta reglas de flujo de correo en el área recomendada para el panel del flujo de correo](../../media/mfi-fix-slow-mail-flow-rules.png)

Al hacer clic en **Ver detalles** en el widget, aparece un control flotante con más información:

- **Regla** : puede desplazar el mouse sobre el resumen para ver todas las condiciones, excepciones y acciones de la regla. Puede hacer clic en el resumen para editar la regla en el centro de administración de Exchange (EAC).
- **Número de mensajes evaluados** : puede hacer clic en **Ver mensajes de ejemplo** para ver los resultados del [seguimiento de mensajes](message-trace-scc.md) para obtener una muestra de los mensajes afectados por la regla.
- **Tiempo promedio invertido en cada mensaje**
- **Tiempo medio invertido en un mensaje** : el valor medio que separa la mitad superior de la mitad inferior de los datos de tiempo.

![Control flotante de detalles que aparece después de hacer clic en ver detalles en la solución solucionar reglas de flujo de correo lenta](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Para obtener más información acerca de las condiciones y excepciones de las reglas de flujo de correo, vea [mail Flow Rule conditions and Exceptions (Predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="see-also"></a>Vea también

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
