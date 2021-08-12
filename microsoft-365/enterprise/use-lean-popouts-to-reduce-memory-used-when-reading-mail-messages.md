---
title: Usar popouts lean para reducir la memoria usada al leer mensajes de correo
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
description: Este artículo contiene información sobre el uso de elementos emergentes lean para mejorar el rendimiento de descarga de mensajes en Outlook en la Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 612774478f5b649901d6eae9dccf332299fa53d38331c6ced847ea8d05be104e
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53840772"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Usar popouts lean para reducir la memoria usada al leer mensajes de correo

Este artículo contiene información para mejorar el rendimiento de descarga de mensajes en Outlook en la Web. Este artículo forma parte del plan de red y el ajuste del rendimiento [para Office 365](./network-planning-and-performance.md) proyecto.
  
Como administrador global Office 365, puede configurar Outlook en la Web para ofrecer _popouts_ lean, una versión más pequeña y con menos memoria de determinados mensajes de correo electrónico en Microsoft Edge o Internet Explorer. Cuando se configuran popouts lean para Outlook en la Web, se cargan los componentes representados del lado servidor que optimizan el rendimiento.
  
> [!NOTE]
> A partir de marzo de 2018, los elementos emergentes lean no están disponibles para los mensajes que especifican restricciones de derechos de uso, como Information Rights Management (IRM).
  
Estas características seguirán funcionando en la ventana principal, pero no están disponibles en los popouts lean:
  
- Complementos de Outlook
  
- Skype Empresarial presencia
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Para configurar popouts lean para todos los usuarios de la Office 365 organización
  
1. [Conectar para Exchange Online con PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).
  
2. Ejecute el cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) con el parámetro LeanPopoutEnabled de la siguiente manera:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Por ejemplo, para habilitar popouts lean para todos los usuarios de la organización:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Para deshabilitar las ventanas emergentes lean para todos los usuarios de la organización:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```