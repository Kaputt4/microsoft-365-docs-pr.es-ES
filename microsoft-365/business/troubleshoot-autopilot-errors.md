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
description: Obtenga información sobre cómo solucionar errores que puede ver mientras trabaja con archivos de dispositivos de AutoPilot en Microsoft 365 Empresa Premium.
ms.openlocfilehash: bec5126696ee322db42e4b7c5cd8e0df485ab2c9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403418"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Solucionar errores de dispositivos de AutoPilot

## <a name="device-file-error-messages"></a>Mensajes de error de archivo de dispositivo

Aquí tienes información sobre algunos de los errores que podrías ver al trabajar con archivos de dispositivos de AutoPilot en Microsoft 365 Empresa Premium. 
  
|**Código de error**|**Corrección que se debe intentar**|
|:-----|:-----|
|Cuerpo de la solicitud no válido  <br/> |Este error debería producirse rara vez, si ve este error, vuelva a intentar la operación.  <br/> |
|El valor hash de hardware para un dispositivo no es correcto.  <br/> |Si ves este error, significa que el valor que proporcionaste en el archivo CSV para el hash de hardware de un dispositivo no es correcto. En primer lugar, compruebe que el valor se ha especificado correctamente. Si piensa que el valor es correcto, pero este error sigue ocurriendo, pida ayuda a su proveedor de hardware.  <br/> |
|Dispositivo asignado a otro inquilino  <br/> |Si ve este error, significa que el valor que proporcionó en el archivo CSV para el número de serie o la clave de producto de uno o más dispositivos no es correcto. En primer lugar, compruebe que el valor se ha especificado correctamente. Si piensa que el valor es correcto, pero este error sigue ocurriendo, pida ayuda a su proveedor de hardware.  <br/> |
|El archivo CSV contiene un número de serie o una clave de producto no válidos  <br/> |Si ve este error, significa que el dispositivo que está intentando registrar ya está registrado por otra organización. Para solucionar este error, pida ayuda a su proveedor de hardware.  <br/> |
|Este dispositivo no es compatible con la configuración mediante AutoPilot  <br/> | Este error significa que el dispositivo no cumple los requisitos de implementación de AutoPilot. Los dispositivos tienen que cumplir estos requisitos:  <br/>  Windows 10, versión 1703 o posteriores.  <br/>  Nuevos dispositivos que no han pasado por la configuración de Windows.  <br/> |
|No se encontró el dispositivo  <br/> |Este error significa que uno o más dispositivos del archivo CSV no están registrados en la organización. Para solucionar este problema, pida ayuda a su proveedor de hardware.  <br/> |
