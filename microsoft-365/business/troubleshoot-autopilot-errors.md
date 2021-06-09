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
# <a name="troubleshoot-autopilot-device-errors"></a>Solucionar errores de dispositivos de AutoPilot

## <a name="device-file-error-messages"></a>Mensajes de error de archivo de dispositivo

Esta es la información sobre algunos de los errores que puedes ver al trabajar con archivos de dispositivo AutoPilot en Microsoft 365 Empresa Premium. 
  
|**Código de error**|**Corrección para probar**|
|:-----|:-----|
|Cuerpo de la solicitud no válida  <br/> |Este error debe ocurrir rara vez, si ve este error, vuelva a intentar la operación.  <br/> |
|El valor hash de hardware para un dispositivo no es correcto.  <br/> |Si ves este error, significa que el valor que proporcionaste en el archivo CSV para el hash de hardware de un dispositivo no es correcto. En primer lugar, compruebe que el valor se presentó correctamente. Si cree que el valor es correcto, pero este error sigue ocurriendo, pida ayuda a su proveedor de hardware.  <br/> |
|Dispositivo asignado a otro inquilino  <br/> |Si ves este error, significa que el valor que proporcionaste en el archivo CSV para el número de serie o la clave de producto de uno o varios dispositivos no es correcto. En primer lugar, compruebe que el valor se presentó correctamente. Si cree que el valor es correcto, pero este error sigue ocurriendo, pida ayuda a su proveedor de hardware.  <br/> |
|El archivo CSV contiene un número de serie o una clave de producto no válidos  <br/> |Si ves este error, significa que el dispositivo que estás intentando registrar ya está registrado por otra organización. Para corregir este error, pida ayuda al proveedor de hardware.  <br/> |
|Este dispositivo no es compatible con la configuración mediante AutoPilot  <br/> | Este error significa que el dispositivo no cumple los requisitos de implementación de AutoPilot. Los dispositivos tienen que cumplir estos requisitos:  <br/>  Windows 10, versión 1703 o posteriores.  <br/>  Nuevos dispositivos que no han pasado por Windows de la caja.  <br/> |
|Dispositivo no encontrado  <br/> |Este error significa que uno o varios dispositivos del archivo CSV no están registrados en la organización. Para solucionar esto, pida ayuda a su proveedor de hardware.  <br/> |
