---
title: Solucionar errores de dispositivos de AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Obtén información sobre cómo solucionar errores que podrías ver mientras trabajas con archivos de dispositivo AutoPilot en Microsoft 365 Empresa Premium.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578095"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="84dfb-103">Solucionar errores de dispositivos de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="84dfb-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="84dfb-104">Mensajes de error de archivo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="84dfb-104">Device file error messages</span></span>

<span data-ttu-id="84dfb-105">Esta es la información sobre algunos de los errores que puedes ver al trabajar con archivos de dispositivo AutoPilot en Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="84dfb-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="84dfb-106">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="84dfb-106">**Error code**</span></span>|<span data-ttu-id="84dfb-107">**Corrección para probar**</span><span class="sxs-lookup"><span data-stu-id="84dfb-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="84dfb-108">Cuerpo de la solicitud no válida</span><span class="sxs-lookup"><span data-stu-id="84dfb-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="84dfb-109">Este error debe ocurrir rara vez, si ve este error, vuelva a intentar la operación.</span><span class="sxs-lookup"><span data-stu-id="84dfb-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="84dfb-110">El valor hash de hardware para un dispositivo no es correcto.</span><span class="sxs-lookup"><span data-stu-id="84dfb-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="84dfb-111">Si ves este error, significa que el valor que proporcionaste en el archivo CSV para el hash de hardware de un dispositivo no es correcto.</span><span class="sxs-lookup"><span data-stu-id="84dfb-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="84dfb-112">En primer lugar, compruebe que el valor se presentó correctamente.</span><span class="sxs-lookup"><span data-stu-id="84dfb-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="84dfb-113">Si cree que el valor es correcto, pero este error sigue ocurriendo, pida ayuda a su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="84dfb-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="84dfb-114">Dispositivo asignado a otro inquilino</span><span class="sxs-lookup"><span data-stu-id="84dfb-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="84dfb-115">Si ves este error, significa que el valor que proporcionaste en el archivo CSV para el número de serie o la clave de producto de uno o varios dispositivos no es correcto.</span><span class="sxs-lookup"><span data-stu-id="84dfb-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="84dfb-116">En primer lugar, compruebe que el valor se presentó correctamente.</span><span class="sxs-lookup"><span data-stu-id="84dfb-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="84dfb-117">Si cree que el valor es correcto, pero este error sigue ocurriendo, pida ayuda a su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="84dfb-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="84dfb-118">El archivo CSV contiene un número de serie o una clave de producto no válidos</span><span class="sxs-lookup"><span data-stu-id="84dfb-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="84dfb-119">Si ves este error, significa que el dispositivo que estás intentando registrar ya está registrado por otra organización.</span><span class="sxs-lookup"><span data-stu-id="84dfb-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="84dfb-120">Para corregir este error, pida ayuda al proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="84dfb-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="84dfb-121">Este dispositivo no es compatible con la configuración mediante AutoPilot</span><span class="sxs-lookup"><span data-stu-id="84dfb-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="84dfb-122">Este error significa que el dispositivo no cumple los requisitos de implementación de AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="84dfb-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="84dfb-123">Los dispositivos tienen que cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="84dfb-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="84dfb-124">Windows 10, versión 1703 o posteriores.</span><span class="sxs-lookup"><span data-stu-id="84dfb-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="84dfb-125">Nuevos dispositivos que no han pasado por la experiencia personalizada de Windows.</span><span class="sxs-lookup"><span data-stu-id="84dfb-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="84dfb-126">Dispositivo no encontrado</span><span class="sxs-lookup"><span data-stu-id="84dfb-126">Device not found</span></span>  <br/> |<span data-ttu-id="84dfb-127">Este error significa que uno o varios dispositivos del archivo CSV no están registrados en la organización.</span><span class="sxs-lookup"><span data-stu-id="84dfb-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="84dfb-128">Para solucionar esto, pida ayuda a su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="84dfb-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
