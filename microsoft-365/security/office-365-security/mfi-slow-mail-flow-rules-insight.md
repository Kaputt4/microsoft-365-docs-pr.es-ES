---
title: Corrección de la información lenta reglas de flujo de correo
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
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre cómo usar la solución Fix Slow mail Flow rules Insight en el centro de seguridad & cumplimiento para identificar y corregir reglas de flujo de correo ineficientes o ineficientes (también conocidas como reglas de transporte) en su organización.
ms.openlocfilehash: bb1c09c2809260be8086059259a1aeec3f1fb3eb
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577178"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Corrección de las reglas de flujo de correo lenta información del centro de seguridad & cumplimiento

Las reglas de flujo de correo ineficiente (también conocidas como reglas de transporte) pueden llevar a retrasos en el flujo de correo de la organización. Esta visión informa de las reglas de flujo de correo que afectan al flujo de correo de su organización. Algunos ejemplos de estos tipos de reglas son:

- Condiciones que usan **son miembros de** grupos grandes.
- Condiciones que usan la coincidencia de patrón de expresiones regulares complejas (regex).
- Condiciones que usan la comprobación de contenido en datos adjuntos.

La opción para **corregir reglas de flujo de correo con lentitud** en el área **recomendada para** el [panel del flujo de correo](mail-flow-insights-v2.md) en el centro de seguridad & cumplimiento le avisa cuando una regla de flujo de correo tarda mucho tiempo en completarse. Esta información sólo aparece cuando se detecta la condición (si no tiene bucles de correo, no verá la información).

Puede usar esta notificación para ayudarle a identificar y ajustar las reglas de flujo de correo para ayudar a reducir los retrasos del flujo de correo.

![Corrección de la información lenta reglas de flujo de correo en el área recomendada para el panel del flujo de correo](../../media/mfi-fix-slow-mail-flow-rules.png)

Al hacer clic en **Ver detalles** en el widget, aparece un control flotante con más información:

- **Regla**: puede desplazar el mouse sobre el resumen para ver todas las condiciones, excepciones y acciones de la regla. Puede hacer clic en el resumen para editar la regla en el centro de administración de Exchange (EAC).
- **Número de mensajes evaluados**: puede hacer clic en **Ver mensajes de ejemplo** para ver los resultados del [seguimiento de mensajes](message-trace-scc.md) para obtener una muestra de los mensajes afectados por la regla.
- **Tiempo promedio invertido en cada mensaje**
- **Tiempo medio invertido en un mensaje**: el valor medio que separa la mitad superior de la mitad inferior de los datos de tiempo.

![Control flotante de detalles que aparece después de hacer clic en ver detalles en la solución solucionar reglas de flujo de correo lenta](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Para obtener más información acerca de las condiciones y excepciones de las reglas de flujo de correo en Exchange Online, consulte [mail Flow Rule conditions and Exceptions (Predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
