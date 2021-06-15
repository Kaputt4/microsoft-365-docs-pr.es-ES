---
title: Validar la configuración de protección de aplicaciones Windows 10 equipos
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Obtén información sobre cómo comprobar que la Microsoft 365 de protección de aplicaciones empresariales ha tenido efecto en los dispositivos Windows 10 usuarios.
ms.openlocfilehash: 464a246a0da65dcffeb70946287ce4fa0e67ae7c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925267"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="326a9-103">Validar la configuración de protección de dispositivos Windows 10 equipos</span><span class="sxs-lookup"><span data-stu-id="326a9-103">Validate device protection settings for Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="326a9-104">Comprobar que Windows 10 directivas de dispositivo están establecidas</span><span class="sxs-lookup"><span data-stu-id="326a9-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="326a9-105">Después de [configurar directivas de dispositivos,](protection-settings-for-windows-10-pcs.md)la directiva puede tardar hasta unas horas en tener efecto en los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="326a9-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="326a9-106">Puedes confirmar que las directivas se han hecho efectivas mirando varias Windows Configuración pantallas en los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="326a9-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="326a9-107">Dado que los usuarios no podrán modificar la configuración de actualización Windows y Antivirus de Windows Defender en sus dispositivos Windows 10, muchas opciones se atenuarán.</span><span class="sxs-lookup"><span data-stu-id="326a9-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="326a9-108">Ve a **Configuración** actualizar las Windows de reinicio de actualización y confirma que todas las opciones \> **&amp;** \>  \>  están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="326a9-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Todas las opciones reiniciar están atenuadas.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="326a9-110">Ve a **Configuración** Actualizar seguridad Windows Opciones avanzadas de actualización y confirma que todas las opciones \> **&amp;** \>  \>  están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="326a9-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows Las opciones de actualizaciones avanzadas están atenuadas.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="326a9-112">Vaya a **Configuración** Actualizar seguridad \> **&amp; Windows** Opciones avanzadas de \>  \> **actualización** \> **Elija cómo se entregan las actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="326a9-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="326a9-113">Confirme que puede ver el mensaje (en rojo) de que algunas opciones de configuración están ocultas o administradas por la organización y todas las opciones están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="326a9-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Elegir cómo se entregan las actualizaciones en la página indica que la configuración está oculta o administrada por la organización.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="326a9-115">Para abrir el Centro Windows Defender seguridad, vaya **a Configuración** Actualizar seguridad Windows Defender haga clic en Abrir Windows Defender Configuración de protección contra virus del Centro de \> **&amp;** \>  \>  \> **&amp;** \> **&amp;** seguridad.</span><span class="sxs-lookup"><span data-stu-id="326a9-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="326a9-116">Compruebe que todas las opciones están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="326a9-116">Verify that all options are grayed out.</span></span> 
    
    ![La configuración de protección contra virus y amenazas está atenuada.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="326a9-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="326a9-118">Related Topics</span></span>

[<span data-ttu-id="326a9-119">Microsoft 365 documentación y recursos para empresas</span><span class="sxs-lookup"><span data-stu-id="326a9-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="326a9-120">Introducción a Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="326a9-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="326a9-121">Administrar Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="326a9-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="326a9-122">Establecer configuraciones de dispositivo para equipos PC con Windows 10</span><span class="sxs-lookup"><span data-stu-id="326a9-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
