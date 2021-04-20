---
title: Nombres de dispositivos
description: Cómo administra Microsoft Managed Desktop los nombres de dispositivos
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
# <a name="device-names"></a><span data-ttu-id="dbfc7-103">Nombres de dispositivos</span><span class="sxs-lookup"><span data-stu-id="dbfc7-103">Device names</span></span>

<span data-ttu-id="dbfc7-104">Microsoft Managed Desktop usa Windows Autopilot, Azure Active Directory y Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="dbfc7-104">Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.</span></span> <span data-ttu-id="dbfc7-105">Para que estos servicios funcionen juntos sin problemas, los dispositivos necesitan nombres uniformes y estandarizados.</span><span class="sxs-lookup"><span data-stu-id="dbfc7-105">For these services to work together seamlessly, devices need consistent, standardized names.</span></span> <span data-ttu-id="dbfc7-106">Microsoft Managed Desktop aplica un formato de nombre estandarizado (con el formato *MMD-%RAND11*) cuando se inscriben dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dbfc7-106">Microsoft Managed Desktop applies a standardized name format (of the form *MMD-%RAND11*) when devices are enrolled.</span></span> <span data-ttu-id="dbfc7-107">Windows Autopilot asigna estos nombres.</span><span class="sxs-lookup"><span data-stu-id="dbfc7-107">Windows Autopilot assigns these names.</span></span> <span data-ttu-id="dbfc7-108">Para obtener más información acerca de Autopilot, vea [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="dbfc7-108">For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

## <a name="automated-name-changes"></a><span data-ttu-id="dbfc7-109">Cambios de nombre automatizados</span><span class="sxs-lookup"><span data-stu-id="dbfc7-109">Automated name changes</span></span>

<span data-ttu-id="dbfc7-110">Si más adelante se cambia el nombre de un dispositivo, Microsoft Managed Desktop cambiará automáticamente el nombre a un nuevo nombre en el formato estandarizado.</span><span class="sxs-lookup"><span data-stu-id="dbfc7-110">If a device gets renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format.</span></span> <span data-ttu-id="dbfc7-111">Este proceso se produce cada cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="dbfc7-111">This process occurs every four hours.</span></span> <span data-ttu-id="dbfc7-112">El cambio de nombre tiene lugar la próxima vez que el usuario reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dbfc7-112">The name change takes place the next time the user restarts the device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbfc7-113">Si el entorno depende de nombres de dispositivo específicos (por ejemplo, para admitir una configuración de red determinada), debes investigar las opciones para quitar esa dependencia antes de inscribirte en Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="dbfc7-113">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="dbfc7-114">Si debe mantener la dependencia de nombre, puede enviar una solicitud a través del portal de [administración](../working-with-managed-desktop/admin-support.md) para deshabilitar la función de cambio de nombre y usar el formato de nombre deseado.</span><span class="sxs-lookup"><span data-stu-id="dbfc7-114">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>