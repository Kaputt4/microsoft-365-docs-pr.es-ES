---
title: Desactivar la sincronización de directorios para Microsoft 365
ms.author: kvice
author: kelleyvice-msft
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
ms.openlocfilehash: 28e0a83bba1a63a7cd1d2f449b9bf3ba34e4862a
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2021
ms.locfileid: "58354205"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Desactivar la sincronización de directorios para Microsoft 365
Puede usar PowerShell para desactivar la sincronización de directorios y convertir los usuarios sincronizados en solo nube. Sin embargo, no se recomienda desactivar la sincronización de directorios como paso de solución de problemas. Si necesita ayuda para solucionar problemas de sincronización de directorios, consulte el artículo Solucionar problemas con la sincronización [de directorios Microsoft 365](fix-problems-with-directory-synchronization.md) directorio. 
  
[Póngase en contacto con](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) el soporte técnico para productos empresariales si es necesario.
  
## <a name="turn-off-directory-synchronization"></a>Desactivar la sincronización de directorios  
Para desactivar la sincronización de directorios:
  
1. En primer lugar, instale el software necesario y conéctese a su Microsoft 365 suscripción. Para obtener instrucciones, [consulte Conectar con el Microsoft Azure Active Directory module para Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Use [Set-MsolDirSyncEnabled para](/previous-versions/azure/dn194097(v=azure.100)) deshabilitar la sincronización de directorios: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Si usa este comando, debe esperar 72 horas antes de volver a activar la sincronización de directorios.
>
