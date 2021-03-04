---
title: Administrar directivas de dispositivos Windows 10 Pro con Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Aprende a administrar directivas de dispositivos de Windows 10 Pro con Microsoft 365 Empresa Premium.
ms.openlocfilehash: 8d3e5107c0b2dfe3a84f31b98d9bd3ff8f7c5e4f
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422128"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="13ce6-103">Administrar directivas de dispositivos Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="13ce6-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="13ce6-104">Puedes usar Microsoft 365 Empresa para garantizar que Windows Defender Antivirus esté activado en dispositivos Windows 10 y que las actualizaciones de Microsoft se descarguen automáticamente en los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="13ce6-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="13ce6-105">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="13ce6-105">Try it!</span></span>

1. <span data-ttu-id="13ce6-106">Inicie sesión en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13ce6-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="13ce6-107">En **Directivas,** elija Agregar directiva.</span><span class="sxs-lookup"><span data-stu-id="13ce6-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="13ce6-108">En el **panel Agregar directiva,** escriba un nombre en **Nombre** de directiva y, a continuación, seleccione Configuración de dispositivo de **Windows 10** en **Tipo de directiva**.</span><span class="sxs-lookup"><span data-stu-id="13ce6-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="13ce6-109">Elige **Proteger dispositivos Windows 10** para ver la sub configuración.</span><span class="sxs-lookup"><span data-stu-id="13ce6-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="13ce6-110">Asegúrate de que **la Ayuda para** proteger los equipos de virus y otras amenazas mediante Windows Defender Antivirus y Mantener los dispositivos Windows **10** actualizados estén activados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="13ce6-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="13ce6-111">En **¿Quién va a obtener esta configuración?**, todos  los usuarios están seleccionados de forma predeterminada, pero puede elegir Cambiar para seleccionar los grupos de seguridad que haya creado.</span><span class="sxs-lookup"><span data-stu-id="13ce6-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="13ce6-112">Para finalizar la creación de la directiva, elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="13ce6-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="13ce6-113">En la **página Agregar directiva,** elija **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="13ce6-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="13ce6-114">En la página principal del Centro de administración, confirme  que la nueva directiva se agregó eligiendo Directivas y revisando la directiva en la **página** Directivas.</span><span class="sxs-lookup"><span data-stu-id="13ce6-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="13ce6-115">Para comprobar que la directiva ha tenido efecto, en el dispositivo Windows 10 de un usuario, vaya a Windows Update, elija Opciones avanzadas y confirme que la configuración está atenuada. </span><span class="sxs-lookup"><span data-stu-id="13ce6-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="13ce6-116">A continuación, haga clic en Elegir cómo se entregan las actualizaciones y confirme que la configuración está atenuada y aparece el siguiente mensaje: Algunas opciones de configuración están ocultas o **administradas por su organización.** </span><span class="sxs-lookup"><span data-stu-id="13ce6-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

