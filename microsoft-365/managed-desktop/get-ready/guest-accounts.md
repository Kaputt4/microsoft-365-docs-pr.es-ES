---
title: Requisitos previos para las cuentas de invitado
description: Directrices de configuración para cuentas de invitado y cómo ajustarlas
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694250"
---
# <a name="prerequisites-for-guest-accounts"></a>Requisitos previos para las cuentas de invitado

Escritorio administrado de Microsoft requiere la siguiente configuración en la organización de Azure AD para el acceso a la cuenta de invitado. Puede ajustar esta configuración en [Azure Portal](https://portal.azure.com) en **Identidades externas / Configuración de colaboración externa:**

-   Para **las restricciones de invitación de invitado establecidas** en Usuarios miembros y usuarios asignados a roles de administrador específicos pueden invitar a usuarios **invitados,** incluidos los invitados con permisos de miembro
-   Para **restricciones de colaboración,** elija cualquiera de estas opciones:
    -   Si selecciona Permitir **que las invitaciones se envíen a cualquier dominio (más inclusivo),** no se requiere ninguna otra configuración.
    -   Si selecciona Denegar invitaciones a los dominios **especificados,** asegúrese de que Microsoft.com no aparece en los dominios de destino.
    -   Si selecciona Permitir invitaciones solo a los dominios **especificados (más**  restrictivos), asegúrese de que Microsoft.com en los dominios de destino.

Si establece restricciones que interactúan con estas opciones de configuración, asegúrese de excluir las Azure Active Directory **modern Workplace Service Accounts**. Por ejemplo, si tiene una directiva de acceso condicional que impide que las cuentas de invitado tengan acceso al portal de Intune, excluya el grupo **Cuentas** de servicio de lugares de trabajo modernos de esta directiva.

## <a name="steps-to-get-ready"></a>Pasos para prepararse

1. Revisar los [requisitos previos del Escritorio administrado de Microsoft](prerequisites.md)
2. Usar las [herramientas para evaluar la preparación](readiness-assessment-tool.md)
3. [Requisitos previos para cuentas invitadas](guest-accounts.md) (este artículo)
4. [Configuración de red para el Escritorio administrado de Microsoft](network.md)
5. [Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft](certs-wifi-lan.md)
6. [Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft](authentication.md)
7. [Aplicaciones en el Escritorio administrado de Microsoft](apps.md)
8. [Preparar unidades asignadas para el Escritorio administrado de Microsoft](mapped-drives.md)
9. [Preparar recursos de impresión para el Escritorio administrado de Microsoft](printing.md)
