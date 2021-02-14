---
title: Usar ventanas emergentes inclinadas para reducir la memoria usada al leer mensajes de correo
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: Este artículo contiene información para usar ventanas emergentes inclinadas para mejorar el rendimiento de descarga de mensajes en Outlook en la Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694114"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Usar ventanas emergentes inclinadas para reducir la memoria usada al leer mensajes de correo

Este artículo contiene información para mejorar el rendimiento de descarga de mensajes en Outlook en la Web. Este artículo forma parte del plan de red y el ajuste [del rendimiento para el proyecto de Office 365.](https://aka.ms/tune)
  
Como administrador global de Office 365, puede configurar Outlook en la Web para ofrecer ventanas emergentes más pequeñas, menos intensivas en memoria de _determinados_ mensajes de correo electrónico en Microsoft Edge o Internet Explorer. Cuando se configuran ventanas emergentes inclinadas para Outlook en la Web, se cargan componentes representados del lado servidor que optimizan el rendimiento.
  
> [!NOTE]
> A partir de marzo de 2018, los elementos emergentes no están disponibles para los mensajes que especifican restricciones de derechos de uso, como Information Rights Management (IRM).
  
Estas características seguirán funcionando en la ventana principal, pero no están disponibles en los elementos emergentes lean:
  
- Complementos de Outlook
  
- Presencia de Skype Empresarial
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Para configurar ventanas emergentes sencillas para todos los usuarios de su organización de Office 365
  
1. [Conéctese a Exchange Online con PowerShell remoto.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx )
  
2. Ejecute el cmdlet [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) con el parámetro LeanPopoutEnabled de la siguiente manera:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Por ejemplo, para habilitar ventanas emergentes sencillas para todos los usuarios de la organización:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Para deshabilitar las ventanas emergentes lean para todos los usuarios de la organización:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
