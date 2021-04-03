---
title: Lista de dispositivos CSV-file
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Obtenga información sobre cómo crear un archivo CSV para AutoPilot en Microsoft 365 para empresas.
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579223"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="c6f03-103">Lista de dispositivos CSV-file</span><span class="sxs-lookup"><span data-stu-id="c6f03-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="c6f03-104">Formato de archivo .csv de lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c6f03-104">Device list .csv file format</span></span>

<span data-ttu-id="c6f03-105">Para administrar e implementar dispositivos a través de Windows Autopilot, necesitarás un archivo .csv que contenga información específica sobre los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c6f03-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="c6f03-106">Las columnas del archivo de lista de dispositivos deben tener los siguientes encabezados en el orden especificado:</span><span class="sxs-lookup"><span data-stu-id="c6f03-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="c6f03-107">Columna A: Número de serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c6f03-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="c6f03-108">Columna B: dejar en blanco</span><span class="sxs-lookup"><span data-stu-id="c6f03-108">Column B: leave blank</span></span>

- <span data-ttu-id="c6f03-109">Columna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="c6f03-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="c6f03-110">Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que generará un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c6f03-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="c6f03-111">Al agregar dispositivos, también debes agregarlos a un perfil.</span><span class="sxs-lookup"><span data-stu-id="c6f03-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="c6f03-112">Un perfil se usa para aplicar perfiles de implementación de AutoPilot a un dispositivo o un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c6f03-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="c6f03-113">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="c6f03-113">Related articles</span></span>

[<span data-ttu-id="c6f03-114">Documentación y recursos de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="c6f03-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="c6f03-115">Introducción a Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="c6f03-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="c6f03-116">Administrar Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="c6f03-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
