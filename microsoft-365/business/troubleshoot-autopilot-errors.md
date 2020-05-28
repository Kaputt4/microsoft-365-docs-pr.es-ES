---
title: Solucionar errores de dispositivos de AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Obtenga información sobre cómo solucionar problemas de errores que puede ver al trabajar con archivos de dispositivos de AutoPilot en Microsoft 365 empresa Premium.
ms.openlocfilehash: bec5126696ee322db42e4b7c5cd8e0df485ab2c9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403418"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="56495-103">Solucionar errores de dispositivos de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="56495-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="56495-104">Mensajes de error de archivo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="56495-104">Device file error messages</span></span>

<span data-ttu-id="56495-105">Aquí encontrará información sobre algunos de los errores que puede ver al trabajar con archivos de dispositivos de AutoPilot en Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="56495-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="56495-106">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="56495-106">**Error code**</span></span>|<span data-ttu-id="56495-107">**Corregir para intentar**</span><span class="sxs-lookup"><span data-stu-id="56495-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56495-108">Cuerpo de la solicitud no válido</span><span class="sxs-lookup"><span data-stu-id="56495-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="56495-109">Este error se debe producir rara vez, si ve este error, vuelva a intentar la operación.</span><span class="sxs-lookup"><span data-stu-id="56495-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="56495-110">El valor de hash de hardware para un dispositivo no es correcto.</span><span class="sxs-lookup"><span data-stu-id="56495-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="56495-111">Si ve este error, significa que el valor que proporcionó en el archivo CSV para el hash de hardware de un dispositivo no es correcto.</span><span class="sxs-lookup"><span data-stu-id="56495-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="56495-112">En primer lugar, compruebe que el valor se escribió correctamente.</span><span class="sxs-lookup"><span data-stu-id="56495-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="56495-113">Si cree que el valor es correcto, pero el error sigue ocurriendo, pida ayuda al proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="56495-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="56495-114">Dispositivo asignado a otro espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="56495-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="56495-115">Si ve este error, significa que el valor que proporcionó en el archivo CSV para el número de serie o la clave de producto de uno o más dispositivos no es correcto.</span><span class="sxs-lookup"><span data-stu-id="56495-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="56495-116">En primer lugar, compruebe que el valor se escribió correctamente.</span><span class="sxs-lookup"><span data-stu-id="56495-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="56495-117">Si cree que el valor es correcto, pero el error sigue ocurriendo, pida ayuda al proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="56495-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="56495-118">El archivo CSV contiene un número de serie o clave de producto no válido</span><span class="sxs-lookup"><span data-stu-id="56495-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="56495-119">Si ve este error, significa que el dispositivo que está intentando registrar ya está registrado en otra organización.</span><span class="sxs-lookup"><span data-stu-id="56495-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="56495-120">Para solucionar este error, pida ayuda al proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="56495-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="56495-121">Este dispositivo no es compatible con el programa de instalación mediante el uso de piloto automático</span><span class="sxs-lookup"><span data-stu-id="56495-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="56495-122">Este error significa que el dispositivo no cumple con los requisitos de la implementación de AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="56495-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="56495-123">Los dispositivos tienen que cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="56495-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="56495-124">Windows 10, versión 1703 o posteriores.</span><span class="sxs-lookup"><span data-stu-id="56495-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="56495-125">Nuevos dispositivos que no han tenido acceso a la experiencia rápida de Windows.</span><span class="sxs-lookup"><span data-stu-id="56495-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="56495-126">No se encontró el dispositivo</span><span class="sxs-lookup"><span data-stu-id="56495-126">Device not found</span></span>  <br/> |<span data-ttu-id="56495-127">Este error significa que uno o más dispositivos del archivo CSV no están registrados en la organización.</span><span class="sxs-lookup"><span data-stu-id="56495-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="56495-128">Para solucionarlo, pida ayuda al proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="56495-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
