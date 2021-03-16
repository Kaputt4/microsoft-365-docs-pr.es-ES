---
title: Obtenga información sobre la directiva predeterminada de prevención de pérdida de datos en Microsoft Teams (versión preliminar)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Obtenga información sobre la directiva predeterminada de prevención de pérdida de datos en Microsoft Teams
ms.openlocfilehash: 3992daf9431dbd87ed5e947a1e5a2b0acd20edce
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826279"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Obtenga información sobre la directiva predeterminada de prevención de pérdida de datos en Microsoft Teams (versión preliminar)

[Las capacidades de prevención](data-loss-prevention-policies.md) de pérdida de datos (DLP) se han ampliado para incluir mensajes de canal y chat de Microsoft Teams, incluidos los mensajes de canal privado. Como parte de esta versión, creamos una directiva DLP predeterminada para los clientes por primera vez en el Centro de cumplimiento.

## <a name="applies-to"></a>Se aplica a

Cualquier inquilino con licencia con una o varias de las siguientes licencias y que tenga usuarios activos de Teams
 
- ME5, 
- MA5, 
- Cumplimiento de E5/A5, 
- IP+G, 
- OE5, 
- Cumplimiento avanzado de O365 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>¿Qué hace la directiva predeterminada?

La directiva DLP predeterminada realiza un seguimiento de todos los números de tarjeta de crédito compartidos interna y externamente en la organización. Esta directiva está predeterminada para todos los usuarios del espacio empresarial. No genera ninguna sugerencia de directiva para los usuarios finales, pero genera un evento Alert y también desencadena un correo electrónico de baja gravedad para el administrador (agregado en la directiva). El administrador puede ver las actividades y editar los detalles de las directivas iniciando sesión en el Centro de cumplimiento.

Los administradores pueden ver esta directiva en la página Directivas de [prevención](https://compliance.microsoft.com/compliancesettings) > centro de cumplimiento.


> [!div class="mx-imgBorder"]
> ![directiva DLP predeterminada de Teams](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Editar o eliminar la directiva predeterminada

Para [editar la directiva predeterminada para un mejor rendimiento o eliminarla,](create-test-tune-dlp-policy.md#tune-a-dlp-policy)solo tiene que usar una cuenta con permisos de administración de cumplimiento **DLP.** Para obtener más información, vea [Permissions](create-test-tune-dlp-policy.md#permissions).

