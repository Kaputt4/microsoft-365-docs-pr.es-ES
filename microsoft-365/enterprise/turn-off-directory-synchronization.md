---
title: Desactivar la sincronización de directorios para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: En este artículo, busque información sobre cómo usar PowerShell para desactivar la sincronización de directorios para Microsoft 365.
ms.openlocfilehash: 26f8729078ea06657ced565db780b57c7e537aa4
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445713"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Desactivar la sincronización de directorios para Microsoft 365
Puede usar PowerShell para desactivar la sincronización de directorios y convertir los usuarios sincronizados en solo nube. Sin embargo, no se recomienda desactivar la sincronización de directorios como paso de solución de problemas. Si necesita ayuda para solucionar problemas de sincronización de directorios, consulte el artículo Solucionar problemas con la sincronización de [directorios para Microsoft 365.](fix-problems-with-directory-synchronization.md) 
  
[Póngase en contacto con](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) el soporte técnico para productos empresariales si es necesario.
  
## <a name="turn-off-directory-synchronization"></a>Desactivar la sincronización de directorios  
Para desactivar la sincronización de directorios:
  
1. En primer lugar, instale el software necesario y conéctese a su suscripción de Microsoft 365. Para obtener instrucciones, consulte [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Use [Set-MsolDirSyncEnabled para](/previous-versions/azure/dn194097(v=azure.100)) deshabilitar la sincronización de directorios: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Si usa este comando, debe esperar 72 horas antes de volver a activar la sincronización de directorios.
>
