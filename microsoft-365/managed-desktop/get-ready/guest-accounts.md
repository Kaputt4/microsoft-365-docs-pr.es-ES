---
title: Requisitos previos para cuentas de invitados
description: Directrices de configuración para cuentas de invitado y cómo ajustarlas
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073247"
---
# <a name="prerequisites-for-guest-accounts"></a>Requisitos previos para cuentas de invitados

Escritorio administrado de Microsoft requiere la siguiente configuración en la organización de Azure AD para el acceso a la cuenta de invitado. Puede ajustar esta configuración en [Azure Portal](https://portal.azure.com) en **Identidades externas/Colaboración externa:**

-   **Los administradores y usuarios del rol de invitador de invitado** pueden invitar establecidos en **Sí**
-   Para **las restricciones de colaboración,** elija cualquiera de estas opciones:
    -   Si selecciona Permitir **que se envíen invitaciones a cualquier dominio (más inclusivo),** no se requiere ninguna otra configuración.
    -   Si selecciona Denegar invitaciones a los dominios **especificados,** asegúrese de que Microsoft.com no aparece en los dominios de destino.
    -   Si selecciona Permitir invitaciones solo a los dominios **especificados (más**  restrictivos), asegúrese de que Microsoft.com en los dominios de destino.

Si establece restricciones que interactúan con esta configuración, asegúrese de excluir las cuentas de servicio de Azure Active Directory **Modern Workplace .** Por ejemplo, si tiene una directiva de acceso condicional que impide que las cuentas de invitado accedan al portal de Intune, excluya el grupo Cuentas de servicio de **Modern Workplace** de esta directiva.

