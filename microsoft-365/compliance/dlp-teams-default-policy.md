---
title: Obtener información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams (versión preliminar)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: Obtenga información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams
ms.openlocfilehash: 61a1ea22362d9e75d605660d29116140f6708003
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60786871"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Obtener información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams (versión preliminar)

[Las capacidades de prevención](dlp-learn-about-dlp.md) de pérdida de datos se han ampliado para incluir Microsoft Teams chat y mensajes de canal, incluidos los mensajes de canal privado. Como parte de esta versión, creamos una directiva DLP predeterminada para Microsoft Teams clientes por primera vez en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a>.

## <a name="applies-to"></a>Se aplica a

Cualquier inquilino con licencia con una o varias de las siguientes licencias y que tenga usuarios Teams activo
 
- ME5, 
- MA5, 
- Cumplimiento de E5/A5, 
- IP+G, 
- OE5, 
- Cumplimiento avanzado de O365 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>¿Qué hace la directiva predeterminada?

La directiva DLP predeterminada para Teams realiza un seguimiento de todos los números de tarjeta de crédito compartidos interna y externamente en la organización. Esta directiva está predeterminada para todos los usuarios del espacio empresarial. No genera ninguna sugerencia de directiva para los usuarios finales, pero genera un evento Alert y también desencadena un correo electrónico de baja gravedad para el administrador (agregado en la directiva). El administrador puede ver las actividades y editar los detalles de las directivas iniciando sesión en el Centro de cumplimiento.

Los administradores pueden ver esta directiva en la página Directivas de [prevención](https://compliance.microsoft.com/compliancesettings) > centro de cumplimiento.


> [!div class="mx-imgBorder"]
> ![directiva Teams DLP predeterminada.](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Editar o eliminar la directiva predeterminada

Para [editar la directiva predeterminada para un mejor rendimiento o eliminarla,](create-test-tune-dlp-policy.md#tune-a-dlp-policy)solo tiene que usar una cuenta con permisos de administración de cumplimiento **DLP.** Para obtener más información, vea [Permissions](create-test-tune-dlp-policy.md#permissions).

