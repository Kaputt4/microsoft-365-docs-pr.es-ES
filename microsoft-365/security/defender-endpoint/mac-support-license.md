---
title: Solucionar problemas de licencia para Microsoft Defender para Endpoint para Mac
description: Solucionar problemas de licencia en Microsoft Defender para Endpoint para Mac.
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
ms.openlocfilehash: 3fb351d9ce8e9beef812e6aaa7d463161a6af8df
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862192"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="5aaf9-104">Solucionar problemas de licencia para Microsoft Defender para Endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="5aaf9-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5aaf9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5aaf9-105">**Applies to:**</span></span>

- [<span data-ttu-id="5aaf9-106">Microsoft Defender para punto de conexión en macOS</span><span class="sxs-lookup"><span data-stu-id="5aaf9-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="5aaf9-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5aaf9-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5aaf9-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5aaf9-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5aaf9-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="5aaf9-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5aaf9-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="5aaf9-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5aaf9-111">Mientras estás pasando por Microsoft Defender para endpoint en [macOS](microsoft-defender-endpoint-mac.md) [y](mac-install-manually.md) pruebas de implementación manual o una prueba de concepto (PoC), es posible que recibas el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="5aaf9-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Imagen de error de licencia](images/no-license-found.png)

<span data-ttu-id="5aaf9-113&quot;>**Mensaje:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5aaf9-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;5aaf9-114&quot;>No se encontró ninguna licencia</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5aaf9-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;5aaf9-115&quot;>Parece que su organización no tiene una licencia para la suscripción a Microsoft 365 Enterprise.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5aaf9-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;5aaf9-116&quot;>Póngase en contacto con el administrador para obtener ayuda.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5aaf9-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;5aaf9-117&quot;>**Causa:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5aaf9-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;5aaf9-118&quot;>Implementó o instaló el paquete de Microsoft Defender para endpoint en macOS (&quot;Descargar paquete de instalación") pero es posible que haya ejecutado el script de configuración ("Descargar paquete de incorporación").</span><span class="sxs-lookup"><span data-stu-id="5aaf9-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="5aaf9-119">**Solución:**</span><span class="sxs-lookup"><span data-stu-id="5aaf9-119">**Solution:**</span></span>

<span data-ttu-id="5aaf9-120">Siga las instrucciones MicrosoftDefenderATPOnboardingMacOs.py documentadas aquí: [Configuración de cliente](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="5aaf9-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

