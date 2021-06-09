---
title: Nombres del dispositivo
description: Cómo Escritorio administrado de Microsoft los nombres de dispositivo
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893980"
---
# <a name="device-names"></a>Nombres del dispositivo

Escritorio administrado de Microsoft usa Windows Autopilot, Azure Active Directory y Microsoft Intune. Para que estos servicios funcionen juntos sin problemas, los dispositivos necesitan nombres uniformes y estandarizados. Escritorio administrado de Microsoft aplica un formato de nombre estandarizado (con el formato *MMD-%RAND11*) cuando se inscriben dispositivos. Windows Autopilot asigna estos nombres. Para obtener más información acerca de Autopilot, vea [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).

## <a name="automated-name-changes"></a>Cambios de nombre automatizados

Si más adelante se cambia el nombre de un dispositivo, Escritorio administrado de Microsoft cambiará automáticamente el nombre a un nuevo nombre en el formato estandarizado. Este proceso se produce cada cuatro horas. El cambio de nombre tiene lugar la próxima vez que el usuario reinicie el dispositivo.

> [!IMPORTANT]
> Si el entorno depende de nombres de dispositivo específicos (por ejemplo, para admitir una configuración de red determinada), debes investigar las opciones para quitar esa dependencia antes de inscribirte en Escritorio administrado de Microsoft. Si debe mantener la dependencia de nombre, puede enviar una solicitud a través del portal de [administración](../working-with-managed-desktop/admin-support.md) para deshabilitar la función de cambio de nombre y usar el formato de nombre deseado.