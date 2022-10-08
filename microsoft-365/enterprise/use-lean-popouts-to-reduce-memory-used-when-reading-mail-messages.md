---
title: Uso de elementos emergentes lean para reducir la memoria usada al leer mensajes de correo
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: Este artículo contiene información para usar elementos emergentes lean para mejorar el rendimiento de descarga de mensajes en Outlook en la Web.
ms.custom: seo-marvel-apr2020
ms.collection: scotvorg
ms.openlocfilehash: d266ba44930adbdc41f06c2e4b1658f9efa9bc35
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191725"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Uso de elementos emergentes lean para reducir la memoria usada al leer mensajes de correo

Este artículo contiene información para mejorar el rendimiento de descarga de mensajes en Outlook en la Web. Este artículo forma parte del [plan de red y el ajuste del rendimiento para Office 365](./network-planning-and-performance.md) proyecto.
  
Como **Office 365 application Administración**, **global admin** o **user Administración**, puede configurar Outlook en la Web para ofrecer _elementos emergentes lean_, una versión más pequeña y menos intensiva de memoria de determinados mensajes de correo electrónico en Microsoft Edge o Internet Explorer. Cuando se configuran elementos emergentes lean para Outlook en la Web, se cargan componentes representados en el lado servidor que optimizan el rendimiento.
  
> [!NOTE]
> A partir de marzo de 2018, los elementos emergentes lean no están disponibles para los mensajes que especifican restricciones de derechos de uso, como Information Rights Management (IRM).
  
Estas características seguirán funcionando en la ventana principal, pero no están disponibles en elementos emergentes lean:
  
- Complementos de Outlook
  
- presencia Skype Empresarial
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Para configurar elementos emergentes lean para todos los usuarios de la organización de Office 365
  
1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).
  
2. Ejecute el cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) con el parámetro LeanPopoutEnabled como se indica a continuación:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Por ejemplo, para habilitar elementos emergentes lean para todos los usuarios de la organización:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Para deshabilitar los elementos emergentes lean para todos los usuarios de la organización:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
