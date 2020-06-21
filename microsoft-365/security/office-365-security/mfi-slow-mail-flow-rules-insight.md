---
title: Reporte de reglas de flujo de correo lento
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 5/3/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las reglas de flujo de correo lentas Insight en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 52ddb6bf5ab6998309fd3122c59636c14b3da1dd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819369"
---
# <a name="slow-mail-flow-rules-insight"></a>Reporte de reglas de flujo de correo lento

Las reglas de flujo de correo ineficiente (también conocidas como reglas de transporte) pueden llevar a retrasos en el flujo de correo de la organización. Esta visión informa de las reglas de flujo de correo que afectan al flujo de correo de su organización. Algunos ejemplos de estos tipos de reglas son:

- Condiciones que usan **son miembros de** grupos grandes.

- Condiciones que usan la coincidencia de patrón de expresiones regulares complejas (regex).

- Condiciones que usan la comprobación de contenido en datos adjuntos.

La información le ayudará a identificar y ajustar las reglas de flujo de correo para ayudar a reducir los retrasos del flujo de correo.

![Una información lenta de reglas de flujo de correo en el panel de flujo de correo del centro de seguridad & cumplimiento](../../media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

Al hacer clic en **Ver detalles**, aparece un panel flotante donde puede revisar la regla. En el panel de flotante, también puede hacer clic en **Ver mensajes de muestra** para ver el tipo de mensajes que se ven afectados por la regla.

![Panel flotante después de hacer clic en ver detalles en una ventana de flujo de correo lenta información sobre las reglas del panel flujo de correo](../../media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="related-topics"></a>Temas relacionados

Para obtener más información acerca de otras indicaciones del flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
