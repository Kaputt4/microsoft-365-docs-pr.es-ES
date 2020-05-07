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
description: Obtenga información sobre cómo crear un archivo CSV para el piloto automático en Microsoft 365 para empresas.
ms.openlocfilehash: c83862675db1372aa2cef27c727c04577b4cf5a3
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064656"
---
# <a name="device-list-csv-file"></a>Archivo CSV de la lista de dispositivos

## <a name="device-list-csv-file-format"></a>Formato de archivo. csv de lista de dispositivos

Para administrar e implementar dispositivos a través de Windows AutoPilot, necesitará un archivo. csv que contenga información específica sobre los dispositivos.
  
Las columnas del archivo de lista de dispositivos deben tener los siguientes encabezados en el orden especificado:
  
- Columna A: Número de serie del dispositivo

- Columna B: dejar en blanco

- Columna C: Hash de hardware

Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que generará un archivo CSV. 

Al agregar dispositivos, también tiene que agregarlos a un perfil. Un perfil se usa para aplicar perfiles de implementación de piloto automático a un dispositivo o a un grupo de dispositivos.
  
## <a name="related-articles"></a>Artículos relacionados

[Documentación y recursos de Microsoft 365 para la empresa](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introducción a Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[Administración de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365/business/manage)
  
