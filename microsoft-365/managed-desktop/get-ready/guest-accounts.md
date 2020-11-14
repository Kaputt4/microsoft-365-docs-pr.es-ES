---
title: Requisitos previos para las cuentas de invitado
description: Instrucciones de configuración para cuentas de invitado y cómo ajustarlas
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
# <a name="prerequisites-for-guest-accounts"></a>Requisitos previos para las cuentas de invitado

Microsoft Managed Desktop requiere la siguiente configuración en su organización de Azure AD para el acceso a la cuenta de invitado. Puede ajustar esta configuración en el [portal de Azure](https://portal.azure.com) en **identidades externas/colaboración externa** :

-   **Los administradores y los usuarios de la función invitador invitado pueden invitar** a que se establezcan en **yes**
-   Para las **restricciones de colaboración** , elija una de estas opciones:
    -   Si selecciona **permitir que se envíen invitaciones a cualquier dominio (en la mayoría de los casos)** , no se requiere ninguna otra configuración.
    -   Si selecciona **denegar invitaciones a los dominios especificados** , asegúrese de que Microsoft.com no aparezca en los dominios de destino.
    -   Si selecciona **permitir invitaciones solo para los dominios especificados (más restrictivos)** , asegúrese de *que Microsoft.com aparezca* en los dominios de destino.

Si establece restricciones que interactúan con esta configuración, asegúrese de excluir las cuentas de **servicio del área de trabajo moderna** de Azure Active Directory. Por ejemplo, si tiene una directiva de acceso condicional que impide que las cuentas de invitado obtengan acceso al portal de Intune, excluya el grupo de **cuentas de servicio del lugar de trabajo moderno** de esta Directiva.

