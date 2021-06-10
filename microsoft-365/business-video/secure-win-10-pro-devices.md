---
title: Administrar Windows 10 Pro de dispositivos con Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtén información sobre cómo administrar Windows 10 Pro de dispositivos con Microsoft 365 Empresa Premium.
ms.openlocfilehash: 0f7cfff227e1ab4ea992414b513e341adbd9ef22
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578692"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="c3328-103">Administrar Windows 10 Pro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c3328-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="c3328-104">Puedes usar Microsoft 365 Empresa para asegurarte de que Antivirus de Windows Defender se activa en Windows 10 dispositivos y las actualizaciones de Microsoft se descargan automáticamente en los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c3328-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="c3328-105">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="c3328-105">Try it!</span></span>

1. <span data-ttu-id="c3328-106">Inicie sesión en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3328-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="c3328-107">En **Directivas,** elija Agregar directiva.</span><span class="sxs-lookup"><span data-stu-id="c3328-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="c3328-108">En el **panel Agregar directiva,** escriba un nombre en **Nombre** de directiva y, a continuación, seleccione Windows 10 Configuración de **dispositivo en** Tipo **de directiva**.</span><span class="sxs-lookup"><span data-stu-id="c3328-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="c3328-109">Elija **Proteger Windows 10 dispositivos** para ver la configuración.</span><span class="sxs-lookup"><span data-stu-id="c3328-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="c3328-110">Asegúrate de que **la Ayuda para** proteger los equipos de virus y otras amenazas mediante Antivirus de Windows Defender y Mantener **Windows 10** dispositivos actualizados estén activados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c3328-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="c3328-111">En **Quién se obtiene esta configuración?**, todos los usuarios están  seleccionados de forma predeterminada, pero puede elegir Cambiar para seleccionar los grupos de seguridad que haya creado.</span><span class="sxs-lookup"><span data-stu-id="c3328-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="c3328-112">Para finalizar la creación de la directiva, elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c3328-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="c3328-113">En la **página Agregar directiva,** elija **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="c3328-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="c3328-114">En la página principal del Centro de administración, confirme  que la nueva directiva se agregó eligiendo Directivas y revisando la directiva en la **página** Directivas.</span><span class="sxs-lookup"><span data-stu-id="c3328-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="c3328-115">Para comprobar que la directiva ha tenido efecto, en el dispositivo Windows 10 de un usuario, vaya a Windows Update, elija **Opciones** avanzadas y confirme que la configuración está atenuada.</span><span class="sxs-lookup"><span data-stu-id="c3328-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="c3328-116">A continuación, haga clic en Elegir cómo se entregan las actualizaciones y confirme que la configuración está atenuada y aparece el siguiente mensaje: Algunas opciones de configuración están ocultas o **administradas por su organización.** </span><span class="sxs-lookup"><span data-stu-id="c3328-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

