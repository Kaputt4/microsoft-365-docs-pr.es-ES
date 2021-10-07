---
title: Nombres del dispositivo
description: Cómo Escritorio administrado de Microsoft los nombres de dispositivo
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: aaf364d4244afaff86f532486597e864cd77209b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150371"
---
# <a name="device-names"></a>Nombres del dispositivo

Escritorio administrado de Microsoft usa Windows Autopilot, Azure Active Directory y Microsoft Intune. Para que estos servicios funcionen juntos sin problemas, los dispositivos necesitan nombres uniformes y estandarizados. Escritorio administrado de Microsoft aplica un formato de nombre estandarizado (con el formato *MMD-%RAND11*) cuando se inscriben dispositivos. Windows Autopilot asigna estos nombres. Para obtener más información acerca de Autopilot, vea [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).

## <a name="automated-name-changes"></a>Cambios de nombre automatizados

Si más adelante se cambia el nombre de un dispositivo, Escritorio administrado de Microsoft cambiará automáticamente el nombre a un nuevo nombre en el formato estandarizado. Este proceso se produce cada cuatro horas. El cambio de nombre tiene lugar la próxima vez que el usuario reinicie el dispositivo.

> [!IMPORTANT]
> Si el entorno depende de nombres de dispositivo específicos (por ejemplo, para admitir una configuración de red determinada), debes investigar las opciones para quitar esa dependencia antes de inscribirte en Escritorio administrado de Microsoft. Si debe mantener la dependencia de nombre, puede enviar una solicitud a través del portal de [administración](../working-with-managed-desktop/admin-support.md) para deshabilitar la función de cambio de nombre y usar el formato de nombre deseado.