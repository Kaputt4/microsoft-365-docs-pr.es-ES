---
title: Archivo CSV de la lista de dispositivos
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Obtenga información sobre cómo crear un archivo CSV para AutoPilo de estaño Microsoft 365 Business.
ms.openlocfilehash: 56d8fb234a1b526192468309c93c638694b92c6e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361361"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="fe103-103">Archivo CSV de la lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="fe103-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="fe103-104">Formato de archivo. csv de lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="fe103-104">Device list .csv file format</span></span>

<span data-ttu-id="fe103-105">Para administrar e implementar dispositivos a través de Windows AutoPilot, necesitará un archivo. csv que contenga información específica sobre los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fe103-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="fe103-106">Las columnas del archivo de lista de dispositivos deben tener los siguientes encabezados en el orden especificado:</span><span class="sxs-lookup"><span data-stu-id="fe103-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="fe103-107">Columna A: Número de serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="fe103-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="fe103-108">Columna B: dejar en blanco</span><span class="sxs-lookup"><span data-stu-id="fe103-108">Column B: leave blank</span></span>

- <span data-ttu-id="fe103-109">Columna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="fe103-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="fe103-110">Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que generará un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="fe103-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="fe103-111">Al agregar dispositivos, también tiene que agregarlos a un perfil.</span><span class="sxs-lookup"><span data-stu-id="fe103-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="fe103-112">Un perfil se usa para aplicar perfiles de implementación de piloto automático a un dispositivo o a un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fe103-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="fe103-113">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="fe103-113">Related articles</span></span>

[<span data-ttu-id="fe103-114">Documentación y recursos de Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="fe103-114">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="fe103-115">Introducción a Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="fe103-115">Get started with Microsoft 365 Business</span></span>](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[<span data-ttu-id="fe103-116">Administrar Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="fe103-116">Manage Microsoft 365 Business</span></span>](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
