---
title: Solucionar problemas de licencia para ATP de Microsoft Defender para Mac
description: Solucionar problemas de licencia en ATP de Microsoft Defender para Mac.
keywords: microsoft, defender, atp, mac, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074467"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="7f6c6-104">Solucionar problemas de licencia para Microsoft Defender para Endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="7f6c6-104">Troubleshoot license issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7f6c6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7f6c6-105">**Applies to:**</span></span>

- [<span data-ttu-id="7f6c6-106">Microsoft Defender para endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="7f6c6-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="7f6c6-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7f6c6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="7f6c6-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f6c6-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7f6c6-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="7f6c6-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7f6c6-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="7f6c6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="7f6c6-111">Mientras estás pasando por Microsoft Defender [](mac-install-manually.md) para endpoint [para Mac](microsoft-defender-endpoint-mac.md) y pruebas de implementación manual o una prueba de concepto (PoC), es posible que recibas el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="7f6c6-111">While you are going through [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Imagen de error de licencia](images/no-license-found.png)

<span data-ttu-id="7f6c6-113">**Mensaje:**</span><span class="sxs-lookup"><span data-stu-id="7f6c6-113">**Message:**</span></span> 

<span data-ttu-id="7f6c6-114">No se encontró ninguna licencia</span><span class="sxs-lookup"><span data-stu-id="7f6c6-114">No license found</span></span>

<span data-ttu-id="7f6c6-115">Parece que su organización no tiene una licencia para la suscripción a Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7f6c6-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="7f6c6-116">Póngase en contacto con el administrador para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="7f6c6-116">Contact your administrator for help.</span></span>

<span data-ttu-id="7f6c6-117">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="7f6c6-117">**Cause:**</span></span> 

<span data-ttu-id="7f6c6-118">Implementó o instaló el paquete de Microsoft Defender para endpoint para macOS ("Descargar paquete de instalación") pero es posible que haya ejecutado el script de configuración ("Descargar paquete de incorporación").</span><span class="sxs-lookup"><span data-stu-id="7f6c6-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="7f6c6-119">**Solución:**</span><span class="sxs-lookup"><span data-stu-id="7f6c6-119">**Solution:**</span></span>

<span data-ttu-id="7f6c6-120">Siga las instrucciones MicrosoftDefenderATPOnboardingMacOs.py documentadas aquí: [Configuración de cliente](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="7f6c6-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

