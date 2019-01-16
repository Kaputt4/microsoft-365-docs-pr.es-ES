---
title: Solucionar problemas de dispositivo de AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Obtenga información sobre cómo solucionar errores de archivo de dispositivo de piloto automático.
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871339"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="ee30e-103">Solucionar problemas de dispositivo de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="ee30e-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="ee30e-104">Mensajes de error de archivo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ee30e-104">Device file error messages</span></span>

<span data-ttu-id="ee30e-105">Información de aquí en algunos de los errores, es posible que vea mientras se trabaja con los archivos de dispositivos de piloto automático en Microsoft Business de 365.</span><span class="sxs-lookup"><span data-stu-id="ee30e-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="ee30e-106">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="ee30e-106">**Error code**</span></span>|<span data-ttu-id="ee30e-107">**Corrección para probar**</span><span class="sxs-lookup"><span data-stu-id="ee30e-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee30e-108">Cuerpo de la solicitud no válido</span><span class="sxs-lookup"><span data-stu-id="ee30e-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="ee30e-109">Este error se debe producirse con muy poca frecuencia, si ve este error, vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="ee30e-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="ee30e-110">Valor de hash de hardware para un dispositivo no es correcta.</span><span class="sxs-lookup"><span data-stu-id="ee30e-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="ee30e-p101">Si ve este error, significa que el valor proporcionado en el archivo CSV para el hash de hardware de un dispositivo no es correcto. En primer lugar, compruebe que el valor se ha escrito correctamente. Si piensa que el valor es correcto, pero este error todavía ocurre, pregunte al proveedor de hardware para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="ee30e-p101">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ee30e-114">Dispositivo asignado a otro inquilino</span><span class="sxs-lookup"><span data-stu-id="ee30e-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="ee30e-p102">Si ve este error, significa que el valor proporcionado en el archivo CSV para el número de serie o la clave de producto de uno o más dispositivos no es correcto. En primer lugar, compruebe que el valor se ha escrito correctamente. Si piensa que el valor es correcto, pero este error todavía ocurre, pregunte al proveedor de hardware para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="ee30e-p102">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ee30e-118">El archivo CSV contiene un número de serie no válido o una clave de producto</span><span class="sxs-lookup"><span data-stu-id="ee30e-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="ee30e-p103">Si ve este error significa que el dispositivo que está al registrar intentar ya está registrado por una organización de otra. Para solucionar este problema, pregunte a su proveedor de hardware para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="ee30e-p103">If you see this error it means that the device you are tyring to register is already registered by an other organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ee30e-121">Este dispositivo no es compatible para el programa de instalación mediante el uso de piloto automático</span><span class="sxs-lookup"><span data-stu-id="ee30e-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="ee30e-p104">Este error significa que el dispositivo no cumple los requisitos de implementación piloto automático. Dispositivos deben cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="ee30e-p104">This error means the device does not meet AutoPilot deployment requirements. Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="ee30e-124">Windows 10, versión 1703 o posteriores.</span><span class="sxs-lookup"><span data-stu-id="ee30e-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="ee30e-125">Nuevos dispositivos que no hayan pasado por una configuración rápida de Windows.</span><span class="sxs-lookup"><span data-stu-id="ee30e-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="ee30e-126">No se encuentra el dispositivo</span><span class="sxs-lookup"><span data-stu-id="ee30e-126">Device not found</span></span>  <br/> |<span data-ttu-id="ee30e-p105">Este error significa que uno o más dispositivos en el archivo CSV no está registrado para su organización. Para solucionar este problema, pregunte a su proveedor de hardware para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="ee30e-p105">This error means that one or more devices in your CSV file is not registered to your organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
