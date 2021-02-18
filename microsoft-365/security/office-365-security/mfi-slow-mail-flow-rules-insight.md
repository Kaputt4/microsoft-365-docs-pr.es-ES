---
title: Corrección de información de reglas de flujo de correo lento
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información sobre las reglas de flujo de correo lentas fix en el Centro de seguridad y cumplimiento de & para identificar y corregir reglas de flujo de correo ineficaces o rotas (también conocidas como reglas de transporte) en su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a50fa0d36cb025f5d0627a2212254b9d08dc5d9c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290698"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Corregir información de reglas de flujo de correo lentas en el Centro de & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Las reglas de flujo de correo ineficientes (también conocidas como reglas de transporte) pueden provocar retrasos en el flujo de correo para su organización. Esta información informa sobre las reglas de flujo de correo que tienen un impacto en el flujo de correo de su organización. Algunos ejemplos de estos tipos de reglas son:

- Condiciones de las **que se usa Es miembro para** grupos grandes.
- Condiciones que usan coincidencia de patrón de expresión regular compleja (regex).
- Condiciones que usan la comprobación de contenido en datos adjuntos.

La  información corregir reglas de  flujo de correo [](mail-flow-insights-v2.md) lentas en el área Recomendado para usted del panel de flujo de correo en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) le notifica cuando una regla de flujo de correo tarda demasiado tiempo en completarse.

Esta información aparece solo después de que se detecte la condición (si no tiene bucles de correo, no verá la información).

Puede usar esta notificación para ayudarle a identificar y ajustar las reglas de flujo de correo para ayudar a reducir los retrasos en el flujo de correo.

![Corregir información de reglas de flujo de correo lentas en el área Recomendada para el panel de flujo de correo](../../media/mfi-fix-slow-mail-flow-rules.png)

Al hacer clic **en Ver detalles** en el widget, aparece un control flotante con más información:

- **Regla:** puede pasar el puntero sobre el resumen para ver todas las condiciones, excepciones y acciones de la regla. Puede hacer clic en el resumen para editar la regla en el Centro de administración de Exchange (EAC).
- **Número de mensajes evaluados:** puede hacer clic [](message-trace-scc.md) en Ver mensajes de ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes afectados por la regla. 
- **Tiempo promedio empleado en cada mensaje**
- **Mediana de tiempo invertido en un mensaje:** el valor intermedio que separa la mitad superior de los datos de la mitad inferior del tiempo.

![Control de detalles que aparece después de hacer clic en Ver detalles en la información de las reglas de flujo de correo de corrección lenta](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Para obtener más información acerca de las condiciones y excepciones en las reglas de flujo de correo, vea Condiciones y excepciones de reglas de flujo de correo [(predicados) en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="see-also"></a>Vea también

Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)
