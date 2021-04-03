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
audience: Admin
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574612"
---
# <a name="prerequisites-for-guest-accounts"></a>Requisitos previos para cuentas de invitados

Microsoft Managed Desktop requiere la siguiente configuración en la organización de Azure AD para el acceso a la cuenta de invitado. Puede ajustar esta configuración en [Azure Portal](https://portal.azure.com) en **Identidades externas / Colaboración externa:**

-   **Los administradores y usuarios del rol invitado** invitado pueden invitar establecido en **Sí**
-   Para **restricciones de colaboración,** elija cualquiera de estas opciones:
    -   Si selecciona Permitir **que las invitaciones se envíen a cualquier dominio (más inclusivo),** no se requiere ninguna otra configuración.
    -   Si selecciona Denegar invitaciones a los dominios **especificados,** asegúrese de que Microsoft.com no aparece en los dominios de destino.
    -   Si selecciona Permitir invitaciones solo a los dominios **especificados (más**  restrictivos), asegúrese de que Microsoft.com en los dominios de destino.

Si establece restricciones que interactúan con esta configuración, asegúrese de excluir las cuentas de servicio de Azure Active Directory **Modern Workplace**. Por ejemplo, si tiene una directiva de acceso condicional que impide que las cuentas de invitado tengan acceso al portal de Intune, excluya el grupo **Cuentas** de servicio de lugares de trabajo modernos de esta directiva.

## <a name="steps-to-get-ready"></a>Pasos para prepararse

1. Revisar [los requisitos previos de Microsoft Managed Desktop](prerequisites.md).
2. Use [herramientas de evaluación de preparación](readiness-assessment-tool.md).
3. [Requisitos previos para cuentas invitadas](guest-accounts.md) (este artículo)
4. [Configuración de red para el Escritorio administrado de Microsoft](network.md)
5. [Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft](certs-wifi-lan.md)
6. [Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft](authentication.md)
7. [Aplicaciones en Escritorio administrado de Microsoft](apps.md)
8. [Preparar unidades asignadas para el Escritorio administrado de Microsoft](mapped-drives.md)
9. [Preparar recursos de impresión para el Escritorio administrado de Microsoft](printing.md)