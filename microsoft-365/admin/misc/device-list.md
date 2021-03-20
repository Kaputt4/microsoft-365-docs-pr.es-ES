---
title: Lista de dispositivos CSV-file
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Obtenga información sobre cómo crear un archivo CSV para AutoPilot en Microsoft 365 para empresas.
ms.openlocfilehash: 78a9012bac054329bdb87b02757f49f30dd44f65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914743"
---
# <a name="device-list-csv-file"></a>Lista de dispositivos CSV-file

## <a name="device-list-csv-file-format"></a>Formato de archivo .csv de lista de dispositivos

Para administrar e implementar dispositivos a través de Windows Autopilot, necesitarás un archivo .csv que contenga información específica sobre los dispositivos.
  
Las columnas del archivo de lista de dispositivos deben tener los siguientes encabezados en el orden especificado:
  
- Columna A: Número de serie del dispositivo

- Columna B: dejar en blanco

- Columna C: Hash de hardware

Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que generará un archivo CSV. 

Al agregar dispositivos, también debes agregarlos a un perfil. Un perfil se usa para aplicar perfiles de implementación de AutoPilot a un dispositivo o un grupo de dispositivos.
  
## <a name="related-articles"></a>Artículos relacionados

[Documentación y recursos de Microsoft 365 para empresas](../../business/index.yml)
  
[Introducción a Microsoft 365 para empresas](../../business/microsoft-365-business-overview.md)
  
[Administrar Microsoft 365 para empresas](../../business/manage.md)
