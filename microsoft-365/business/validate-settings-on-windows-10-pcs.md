---
title: Validar la configuración de protección de aplicaciones en PC con Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Obtenga información sobre cómo validar la configuración de protección de aplicaciones empresariales de Microsoft 365 en dispositivos Windows 10.
ms.openlocfilehash: 5ab91d65fa7bd40ebc118df217c9711b7bbfe7a4
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286778"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="85496-103">Validar la configuración de protección de dispositivos en equipos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="85496-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="85496-104">Comprobar que las directivas de dispositivos de Windows 10 están definidas</span><span class="sxs-lookup"><span data-stu-id="85496-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="85496-105">Una vez que haya [configurado las directivas de dispositivos](protection-settings-for-windows-10-pcs.md), la Directiva puede tardar hasta unas pocas horas en aplicarse a los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="85496-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="85496-106">Para confirmar que las directivas tuvieron efecto, consulte varias pantallas de configuración de Windows en los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="85496-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="85496-107">Como los usuarios no podrán modificar la configuración de Windows Update y antivirus de Windows Defender en sus dispositivos con Windows 10, se mostrarán muchas opciones en gris.</span><span class="sxs-lookup"><span data-stu-id="85496-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, a lot of those options will be greyed out.</span></span>
  
1. <span data-ttu-id="85496-108">Vaya a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> \*\*\*\* restart y confirme que todas las opciones están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="85496-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out.</span></span> 
    
    ![Todas las opciones de reInicio están atenuadas.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="85496-110">Vaya a **configuración** \> **actualizar &amp; seguridad** \> **Windows Update** \> **Opciones avanzadas** y confirme que toda la configuración está atenuada.</span><span class="sxs-lookup"><span data-stu-id="85496-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out.</span></span> 
    
    ![Las opciones de actualizaciones avanzadas de Windows están en gris.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="85496-112">Ir a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> **Opciones** \> avanzadas **Elija cómo se entregan las actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="85496-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="85496-113">Confirme que puede ver el mensaje (en rojo) que la organización está ocultando o administrando, y que todas las opciones están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="85496-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are greyed out.</span></span>
    
    ![Elegir cómo se entregan las actualizaciones la página indica que la configuración está oculta o administrada por la organización.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="85496-115">Para abrir el centro de seguridad de Windows Defender, vaya a **configuración** \> **actualización &amp; seguridad** \> **Windows Defender** \> , haga clic en abrir el tema de \> \*\*\*\* \*\*antivirus &amp; del centro de seguridad de Windows Defender \*\* \> **configuración de &amp; protección contra amenazas de virus**de protección.</span><span class="sxs-lookup"><span data-stu-id="85496-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="85496-116">Compruebe que todas las opciones están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="85496-116">Verify that all options are greyed out.</span></span> 
    
    ![La configuración de protección contra virus y amenazas está atenuada.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="85496-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="85496-118">Related Topics</span></span>

[<span data-ttu-id="85496-119">Documentación y recursos de Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="85496-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="85496-120">Introducción a Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="85496-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="85496-121">Administrar Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="85496-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="85496-122">Establecer configuraciones de dispositivo para equipos PC con Windows 10</span><span class="sxs-lookup"><span data-stu-id="85496-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

