---
title: Validar la configuración de protección de aplicaciones en PC con Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Obtenga información sobre cómo validar la configuración de protección de aplicación de Microsoft 365 Business en los dispositivos de Windows 10.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871326"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="f868e-103">Validar la configuración de la protección de dispositivo en equipos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="f868e-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="f868e-104">Comprobar que se establecen las directivas de dispositivo de Windows 10</span><span class="sxs-lookup"><span data-stu-id="f868e-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="f868e-p101">Después de [configurar las directivas de dispositivos](protection-settings-for-windows-10-pcs.md), pueden tardar hasta unas cuantas horas para la directiva surta efecto en los dispositivos de los usuarios. Puede confirmar que las directivas entraron en vigor observando varias pantallas de configuración de Windows en los dispositivos de los usuarios. Debido a que los usuarios no podrán modificar la configuración de actualización de Windows y Windows Defender Antivirus en sus dispositivos de Windows 10, una gran cantidad de esas opciones estará desactivada.</span><span class="sxs-lookup"><span data-stu-id="f868e-p101">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices. You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices. Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, a lot of those options will be greyed out.</span></span>
  
1. <span data-ttu-id="f868e-108">Vaya a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> **Opciones de reinicio** y confirme que no todas las opciones están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="f868e-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out.</span></span> 
    
    ![Todas las opciones de reinicio no están habilitadas.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="f868e-110">Vaya a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> **Opciones avanzadas** y confirme que no todas las opciones están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="f868e-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out.</span></span> 
    
    ![Opciones avanzadas de Windows para las actualizaciones son todos atenuadas.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="f868e-112">Vaya a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> **Opciones avanzadas** \> **Elegir cómo se entregan las actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="f868e-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="f868e-113">Confirme que puede ver el mensaje (en rojo) que algunas opciones de configuración están ocultos o administrados por la organización, y todas las opciones no están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="f868e-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are greyed out.</span></span>
    
    ![Elegir cómo se entregan las actualizaciones de página indica configuración está oculta o administrada por la organización.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="f868e-115">Para abrir el centro de seguridad de Windows Defender, vaya a **configuración de** \> **actualización &amp; seguridad** \> **Windows Defender** \> haga clic en **Centro de seguridad de abrir Windows Defender** \> **Virus &amp; subproceso protección** \> **Virus &amp; configuración de la protección de amenazas**.</span><span class="sxs-lookup"><span data-stu-id="f868e-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="f868e-116">Compruebe que todas las opciones no están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="f868e-116">Verify that all options are greyed out.</span></span> 
    
    ![La configuración de la protección contra Virus y amenazas no está habilitada.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="f868e-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f868e-118">Related Topics</span></span>

[<span data-ttu-id="f868e-119">Documentación y recursos de Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="f868e-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="f868e-120">Introducción a Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="f868e-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="f868e-121">Administrar Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="f868e-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="f868e-122">Establecer configuraciones de dispositivo para equipos PC con Windows 10</span><span class="sxs-lookup"><span data-stu-id="f868e-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

