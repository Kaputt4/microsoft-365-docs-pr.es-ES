---
title: Validar la configuración de protección de aplicaciones en PC con Windows 10
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
ms.openlocfilehash: fcb463fd98f692f7d4802689e0c03fe4e3e648a1
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579850"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="76761-103">Validar la configuración de protección de dispositivos Windows 10 equipos</span><span class="sxs-lookup"><span data-stu-id="76761-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="76761-104">Comprobar que Windows 10 directivas de dispositivo están establecidas</span><span class="sxs-lookup"><span data-stu-id="76761-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="76761-105">Después de [configurar directivas de dispositivos,](protection-settings-for-windows-10-pcs.md)la directiva puede tardar hasta unas horas en tener efecto en los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="76761-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="76761-106">Puedes confirmar que las directivas se han hecho efectivas mirando varias Windows Configuración pantallas en los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="76761-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="76761-107">Dado que los usuarios no podrán modificar la configuración de actualización Windows y Antivirus de Windows Defender en sus dispositivos Windows 10, muchas opciones se atenuarán.</span><span class="sxs-lookup"><span data-stu-id="76761-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="76761-108">Ve a **Configuración** actualizar las Windows de reinicio de actualización y confirma que todas las opciones \> **&amp;** \>  \>  están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="76761-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Todas las opciones reiniciar están atenuadas.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="76761-110">Ve a **Configuración** Actualizar seguridad Windows Opciones avanzadas de actualización y confirma que todas las opciones \> **&amp;** \>  \>  están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="76761-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows Las opciones de actualizaciones avanzadas están atenuadas.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="76761-112">Vaya a **Configuración** Actualizar seguridad \> **&amp; Windows** Opciones avanzadas de \>  \> **actualización** \> **Elija cómo se entregan las actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="76761-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="76761-113">Confirme que puede ver el mensaje (en rojo) de que algunas opciones de configuración están ocultas o administradas por la organización y todas las opciones están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="76761-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Elegir cómo se entregan las actualizaciones en la página indica que la configuración está oculta o administrada por la organización.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="76761-115">Para abrir el Centro Windows Defender seguridad, vaya **a Configuración** Actualizar seguridad Windows Defender haga clic en Abrir Windows Defender Configuración de protección contra virus del Centro de \> **&amp;** \>  \>  \> **&amp;** \> **&amp;** seguridad.</span><span class="sxs-lookup"><span data-stu-id="76761-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="76761-116">Compruebe que todas las opciones están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="76761-116">Verify that all options are grayed out.</span></span> 
    
    ![La configuración de protección contra virus y amenazas está atenuada.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="76761-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="76761-118">Related Topics</span></span>

[<span data-ttu-id="76761-119">Microsoft 365 documentación y recursos para empresas</span><span class="sxs-lookup"><span data-stu-id="76761-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="76761-120">Introducción a Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="76761-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="76761-121">Administrar Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="76761-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="76761-122">Establecer configuraciones de dispositivo para equipos PC con Windows 10</span><span class="sxs-lookup"><span data-stu-id="76761-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
