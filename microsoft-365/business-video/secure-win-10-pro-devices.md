---
title: Administrar directivas de dispositivos windows 10 Pro con Microsoft 365 Empresa Premium
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtén información sobre cómo administrar directivas de dispositivos de Windows 10 Pro con Microsoft 365 Empresa Premium.
ms.openlocfilehash: f42c175543ae16ae645c17997b20ed67aa5d705c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926011"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="63e0b-103">Administrar directivas de dispositivos Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="63e0b-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="63e0b-104">Puede usar Microsoft 365 Empresa para asegurarse de que Windows Defender Antivirus está activado en dispositivos Windows 10 y que las actualizaciones de Microsoft se descargan automáticamente en los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="63e0b-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="63e0b-105">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="63e0b-105">Try it!</span></span>

1. <span data-ttu-id="63e0b-106">Inicie sesión en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="63e0b-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="63e0b-107">En **Directivas,** elija Agregar directiva.</span><span class="sxs-lookup"><span data-stu-id="63e0b-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="63e0b-108">En el **panel Agregar directiva,** escribe un nombre en **Nombre** de directiva y, a continuación, selecciona Configuración de dispositivo de **Windows 10** en **Tipo de directiva.**</span><span class="sxs-lookup"><span data-stu-id="63e0b-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="63e0b-109">Elige **Proteger dispositivos Windows 10** para ver la sub configuración.</span><span class="sxs-lookup"><span data-stu-id="63e0b-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="63e0b-110">Asegúrate de proteger los equipos de virus y otras amenazas con **Windows Defender Antivirus** y mantener los dispositivos **Windows 10** actualizados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="63e0b-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="63e0b-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span><span class="sxs-lookup"><span data-stu-id="63e0b-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="63e0b-112">Para terminar de crear la directiva, elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="63e0b-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="63e0b-113">En la **página Agregar directiva,** elija **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="63e0b-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="63e0b-114">En la página principal del centro de administración, confirme  que se ha agregado la nueva directiva eligiendo Directivas y revisando la directiva en la **página** Directivas.</span><span class="sxs-lookup"><span data-stu-id="63e0b-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="63e0b-115">Para comprobar que la directiva ha tenido efecto, en el dispositivo Windows 10 de un usuario, ve a Windows Update, elige Opciones avanzadas y confirma que la configuración está atenuada. </span><span class="sxs-lookup"><span data-stu-id="63e0b-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="63e0b-116">A **continuación,** haga clic en Elegir cómo se entregan las actualizaciones y confirme que la configuración está atenuada y aparece el siguiente mensaje: Algunas opciones de configuración están ocultas o **administradas por su organización.**</span><span class="sxs-lookup"><span data-stu-id="63e0b-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

