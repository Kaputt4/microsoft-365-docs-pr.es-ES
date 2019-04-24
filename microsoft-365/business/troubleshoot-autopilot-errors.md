---
title: Solucionar errores de dispositivos de AutoPilot
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
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Obtenga información sobre cómo solucionar errores de archivos de dispositivos de autoPilot.
ms.openlocfilehash: 9d4a47f78c38d8c076f5b3876a36b6bf46eaaaf3
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279846"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Solucionar errores de dispositivos de AutoPilot

## <a name="device-file-error-messages"></a>Mensajes de error de archivo de dispositivo

Aquí encontrará información sobre algunos de los errores que puede ver al trabajar con archivos de dispositivos de autoPilot en Microsoft 365 Business. 
  
|**Código de error**|**Corregir para intentar**|
|:-----|:-----|
|Cuerpo de la solicitud no válido  <br/> |Este error se debe producir rara vez, si ve este error, vuelva a intentar la operación.  <br/> |
|El valor de hash de hardware para un dispositivo no es correcto.  <br/> |Si ve este error, significa que el valor que proporcionó en el archivo CSV para el hash de hardware de un dispositivo no es correcto. En primer lugar, compruebe que el valor se escribió correctamente. Si cree que el valor es correcto, pero el error sigue ocurriendo, pida ayuda al proveedor de hardware.  <br/> |
|Dispositivo asignado a otro espacio empresarial  <br/> |Si ve este error, significa que el valor que proporcionó en el archivo CSV para el número de serie o la clave de producto de uno o más dispositivos no es correcto. En primer lugar, compruebe que el valor se escribió correctamente. Si cree que el valor es correcto, pero el error sigue ocurriendo, pida ayuda al proveedor de hardware.  <br/> |
|El archivo CSV contiene un número de serie o clave de producto no válido  <br/> |Si ve este error significa que el dispositivo que está tyring a registrar ya está registrado por otra organización. Para solucionarlo, pida ayuda al proveedor de hardware.  <br/> |
|Este dispositivo no es compatible con el programa de instalación mediante el uso de piloto automático  <br/> | Este error significa que el dispositivo no cumple con los requisitos de la implementación de autoPilot. Los dispositivos tienen que cumplir estos requisitos:  <br/>  Windows 10, versión 1703 o posteriores.  <br/>  Los nuevos dispositivos que no han pasado por una configuración rápida de Windows.  <br/> |
|No se encontró el dispositivo  <br/> |Este error significa que uno o más dispositivos del archivo CSV no están registrados en la organización. Para solucionarlo, pida ayuda al proveedor de hardware.  <br/> |
   
