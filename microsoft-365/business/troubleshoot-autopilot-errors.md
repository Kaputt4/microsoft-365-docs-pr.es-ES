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
# <a name="troubleshoot-autopilot-device-errors"></a>Solucionar problemas de dispositivo de AutoPilot

## <a name="device-file-error-messages"></a>Mensajes de error de archivo de dispositivo

Información de aquí en algunos de los errores, es posible que vea mientras se trabaja con los archivos de dispositivos de piloto automático en Microsoft Business de 365. 
  
|**Código de error**|**Corrección para probar**|
|:-----|:-----|
|Cuerpo de la solicitud no válido  <br/> |Este error se debe producirse con muy poca frecuencia, si ve este error, vuelva a intentarlo.  <br/> |
|Valor de hash de hardware para un dispositivo no es correcta.  <br/> |Si ve este error, significa que el valor proporcionado en el archivo CSV para el hash de hardware de un dispositivo no es correcto. En primer lugar, compruebe que el valor se ha escrito correctamente. Si piensa que el valor es correcto, pero este error todavía ocurre, pregunte al proveedor de hardware para obtener ayuda.  <br/> |
|Dispositivo asignado a otro inquilino  <br/> |Si ve este error, significa que el valor proporcionado en el archivo CSV para el número de serie o la clave de producto de uno o más dispositivos no es correcto. En primer lugar, compruebe que el valor se ha escrito correctamente. Si piensa que el valor es correcto, pero este error todavía ocurre, pregunte al proveedor de hardware para obtener ayuda.  <br/> |
|El archivo CSV contiene un número de serie no válido o una clave de producto  <br/> |Si ve este error significa que el dispositivo que está al registrar intentar ya está registrado por una organización de otra. Para solucionar este problema, pregunte a su proveedor de hardware para obtener ayuda.  <br/> |
|Este dispositivo no es compatible para el programa de instalación mediante el uso de piloto automático  <br/> | Este error significa que el dispositivo no cumple los requisitos de implementación piloto automático. Dispositivos deben cumplir estos requisitos:  <br/>  Windows 10, versión 1703 o posteriores.  <br/>  Nuevos dispositivos que no hayan pasado por una configuración rápida de Windows.  <br/> |
|No se encuentra el dispositivo  <br/> |Este error significa que uno o más dispositivos en el archivo CSV no está registrado para su organización. Para solucionar este problema, pregunte a su proveedor de hardware para obtener ayuda.  <br/> |
   
