---
title: Restaurar archivos en cuarentena en Microsoft Defender AV
description: Puede restaurar archivos y carpetas que fueron puestos en cuarentena por Microsoft Defender AV.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: e0253c4ac7d92c91e3fda45681568d721645f2b0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275389"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a><span data-ttu-id="25fe0-103">Restaurar archivos en cuarentena en Microsoft Defender AV</span><span class="sxs-lookup"><span data-stu-id="25fe0-103">Restore quarantined files in Microsoft Defender AV</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="25fe0-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="25fe0-104">**Applies to:**</span></span>

- [<span data-ttu-id="25fe0-105">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="25fe0-105">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="25fe0-106">Si Antivirus de Microsoft Defender está configurado para detectar y corregir amenazas en el dispositivo, Antivirus de Microsoft Defender pone en cuarentena archivos sospechosos.</span><span class="sxs-lookup"><span data-stu-id="25fe0-106">If Microsoft Defender Antivirus is configured to detect and remediate threats on your device, Microsoft Defender Antivirus quarantines suspicious files.</span></span> <span data-ttu-id="25fe0-107">Si está seguro de que un archivo en cuarentena no es una amenaza, puede restaurarlo.</span><span class="sxs-lookup"><span data-stu-id="25fe0-107">If you are certain a quarantined file is not a threat, you can restore it.</span></span>

1. <span data-ttu-id="25fe0-108">Abra **Seguridad de Windows**.</span><span class="sxs-lookup"><span data-stu-id="25fe0-108">Open **Windows Security**.</span></span>
2. <span data-ttu-id="25fe0-109">Seleccione **Protección contra & virus y,** a continuación, haga clic en Historial de **protección**.</span><span class="sxs-lookup"><span data-stu-id="25fe0-109">Select **Virus & threat protection** and then click **Protection history**.</span></span>
3. <span data-ttu-id="25fe0-110">En la lista de todos los elementos recientes, filtre en **Elementos en cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="25fe0-110">In the list of all recent items, filter on **Quarantined Items**.</span></span>
4. <span data-ttu-id="25fe0-111">Seleccione un elemento que desee conservar y haga una acción, como restaurar.</span><span class="sxs-lookup"><span data-stu-id="25fe0-111">Select an item you want to keep, and take an action, such as restore.</span></span>

> [!TIP]
> <span data-ttu-id="25fe0-112">La restauración de un archivo desde la cuarentena también se puede realizar mediante el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="25fe0-112">Restoring a file from quarantine can also be done using Command Prompt.</span></span> <span data-ttu-id="25fe0-113">Consulte [Restore a file from quarantine](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine).</span><span class="sxs-lookup"><span data-stu-id="25fe0-113">See [Restore a file from quarantine](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine).</span></span> 

## <a name="related-articles"></a><span data-ttu-id="25fe0-114">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="25fe0-114">Related articles</span></span>

- [<span data-ttu-id="25fe0-115">Configurar la corrección para exámenes</span><span class="sxs-lookup"><span data-stu-id="25fe0-115">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
- [<span data-ttu-id="25fe0-116">Revisar los resultados del examen</span><span class="sxs-lookup"><span data-stu-id="25fe0-116">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md)
- [<span data-ttu-id="25fe0-117">Configurar y validar exclusiones según el nombre de archivo, la extensión y la ubicación de la carpeta</span><span class="sxs-lookup"><span data-stu-id="25fe0-117">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="25fe0-118">Configurar y validar exclusiones para archivos abiertos por procesos</span><span class="sxs-lookup"><span data-stu-id="25fe0-118">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="25fe0-119">Configurar Antivirus de Microsoft Defender exclusiones en Windows Server</span><span class="sxs-lookup"><span data-stu-id="25fe0-119">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)