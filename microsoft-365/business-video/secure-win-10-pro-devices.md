---
title: Administración de directivas de dispositivo de Windows 10 Pro con Microsoft 365 empresa Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Obtenga información sobre cómo administrar las directivas de dispositivo de Windows 10 Pro con Microsoft 365 empresa Premium.
ms.openlocfilehash: 9052859f03035a76bf69b7c8c23c75ae00353846
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703192"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="05520-103">Administrar directivas de dispositivo de Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="05520-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="05520-104">Puede usar Microsoft 365 Business para asegurarse de que el antivirus de Windows Defender está activado en dispositivos con Windows 10 y que las actualizaciones de Microsoft se descargan automáticamente en los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="05520-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="05520-105">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="05520-105">Try it!</span></span>

1. <span data-ttu-id="05520-106">Inicie sesión en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05520-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="05520-107">En **directivas**, elija Agregar Directiva.</span><span class="sxs-lookup"><span data-stu-id="05520-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="05520-108">En el panel **Agregar Directiva** , escriba un nombre en **nombre** de la Directiva y, a continuación, seleccione **configuración de dispositivo Windows 10** en **tipo de directiva**.</span><span class="sxs-lookup"><span data-stu-id="05520-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="05520-109">Elija **proteger dispositivos Windows 10** para ver las configuraciones secundarias.</span><span class="sxs-lookup"><span data-stu-id="05520-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="05520-110">Asegúrate de que **proteger los equipos PC contra virus y otras amenazas con el antivirus de Windows Defender** y **mantener los dispositivos con Windows 10 actualizados automáticamente** está activado.</span><span class="sxs-lookup"><span data-stu-id="05520-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="05520-111">En ¿ **quién recibirá esta configuración?**, todos los usuarios están seleccionados de forma predeterminada, pero puede elegir **cambiar** para seleccionar los grupos de seguridad que haya creado.</span><span class="sxs-lookup"><span data-stu-id="05520-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="05520-112">Para finalizar la creación de la Directiva, elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="05520-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="05520-113">En la página **Agregar Directiva** , elija **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="05520-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="05520-114">En la Página principal del centro de administración, confirme que se ha agregado la nueva Directiva eligiendo **directivas** y revisando la Directiva en la página **directivas** .</span><span class="sxs-lookup"><span data-stu-id="05520-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="05520-115">Para comprobar que la Directiva ha surtido efecto, en el dispositivo Windows 10 de un usuario, vaya a Windows Update, elija **Opciones avanzadas** y confirme que la configuración está atenuada.</span><span class="sxs-lookup"><span data-stu-id="05520-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="05520-116">A continuación, haga clic en **elegir cómo se van a entregar las actualizaciones** y asegúrese de que la configuración está atenuada y aparece el mensaje siguiente: **algunas opciones de configuración están ocultas o están administradas por la organización**.</span><span class="sxs-lookup"><span data-stu-id="05520-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

