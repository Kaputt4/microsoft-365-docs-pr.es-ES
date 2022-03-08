---
title: Nombres del dispositivo
description: Cómo administra Microsoft Managed Desktop los nombres de dispositivos
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: fe29027dab3b3395c14729ee7e04cbe7cebf7261
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317169"
---
# <a name="device-names"></a>Nombres del dispositivo

Microsoft Managed Desktop usa Windows Autopilot, Azure Active Directory y Microsoft Intune.

Para que estos servicios funcionen juntos sin problemas, los dispositivos necesitan nombres uniformes y estandarizados. Microsoft Managed Desktop aplica un formato de nombre estandarizado (del `MMD-%RAND11`formulario) cuando se inscriben dispositivos. Windows Autopilot asigna estos nombres. Para obtener más información acerca de Autopilot, consulte [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).

## <a name="automated-name-changes"></a>Cambios de nombre automatizados

Si más adelante se cambia el nombre de un dispositivo, Microsoft Managed Desktop cambiará automáticamente su nombre por un nuevo nombre en el formato estandarizado. Este proceso se produce cada cuatro horas. El cambio de nombre tiene lugar la próxima vez que el usuario reinicie el dispositivo.

> [!IMPORTANT]
> Si el entorno depende de nombres de dispositivo específicos (por ejemplo, para admitir una configuración de red determinada), debes investigar las opciones para quitar esa dependencia antes de inscribirte en Microsoft Managed Desktop.<br><br>Si debe mantener la dependencia de nombre, puede enviar una solicitud a través del [portal de administración](../working-with-managed-desktop/admin-support.md) para deshabilitar la función de cambio de nombre y usar el formato de nombre deseado.
