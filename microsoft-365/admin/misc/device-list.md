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
