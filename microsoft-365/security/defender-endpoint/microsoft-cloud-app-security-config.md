---
title: Configurar la integración de Microsoft Cloud App Security
ms.reviewer: ''
description: Obtén información sobre cómo activar la configuración para habilitar la integración de Microsoft Defender para endpoints con Microsoft Cloud App Security.
keywords: nube, aplicación, seguridad, configuración, integración, detección, informe
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ddf32b26191826ab6ecbad6b9d047ac7bbb6276a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076571"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9b61b-104">Configurar Microsoft Cloud App Security en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="9b61b-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9b61b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9b61b-105">**Applies to:**</span></span>
- [<span data-ttu-id="9b61b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9b61b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9b61b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b61b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9b61b-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="9b61b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9b61b-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="9b61b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="9b61b-110">Para beneficiarse de las señales de detección de aplicaciones en la nube de Microsoft Defender para endpoint, activa la integración de Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9b61b-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="9b61b-111">Esta característica estará disponible con una licencia E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) en dispositivos que ejecutan Windows 10, versión 1709 (compilación del sistema operativo 16299.1085 con [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, versión 1803 (compilación del sistema operativo 17134.704 con [KB4493464),](https://support.microsoft.com/help/4493464)Windows 10, versión 1809 (compilación del sistema operativo 17763.379 con [KB4489899)](https://support.microsoft.com/help/4489899)o versiones posteriores de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9b61b-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="9b61b-112">Consulta La integración de Microsoft Defender para [endpoints con Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) para obtener una integración detallada de Microsoft Defender para Endpoint con Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9b61b-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9b61b-113">Habilitar Microsoft Cloud App Security en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="9b61b-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="9b61b-114">En el panel de navegación, seleccione **Configuración de**  >  **preferencias Características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="9b61b-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="9b61b-115">Seleccione **Microsoft Cloud App Security** y cambie la alternancia a **On**.</span><span class="sxs-lookup"><span data-stu-id="9b61b-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="9b61b-116">Haga clic **en Guardar preferencias**.</span><span class="sxs-lookup"><span data-stu-id="9b61b-116">Click **Save preferences**.</span></span>

<span data-ttu-id="9b61b-117">Una vez activado, Microsoft Defender para Endpoint iniciará inmediatamente el reenvío de señales de detección a Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9b61b-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="9b61b-118">Ver los datos recopilados</span><span class="sxs-lookup"><span data-stu-id="9b61b-118">View the data collected</span></span>

<span data-ttu-id="9b61b-119">Para ver y obtener acceso a datos de Microsoft Defender para puntos de conexión en Microsoft Cloud Apps Security, consulta [Investigar dispositivos en Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="9b61b-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="9b61b-120">Para obtener más información acerca de la detección en la nube, consulta [Trabajar con aplicaciones detectadas.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="9b61b-120">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="9b61b-121">Si estás interesado en probar Microsoft Cloud App Security, consulta Prueba de [Microsoft Cloud App Security](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span><span class="sxs-lookup"><span data-stu-id="9b61b-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="9b61b-122">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="9b61b-122">Related topic</span></span>
- [<span data-ttu-id="9b61b-123">Integración de Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9b61b-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
