---
title: Requisitos previos para las cuentas de invitado
description: Directrices de configuración para cuentas de invitado y cómo ajustarlas
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: db07ca3bb7577aed7b334ba21893f6fe026819a0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197142"
---
# <a name="prerequisites-for-guest-accounts"></a>Requisitos previos para las cuentas de invitado

## <a name="external-collaboration-settings"></a>Configuración de la colaboración externa

Escritorio administrado de Microsoft recomienda la siguiente configuración en la organización de Azure AD para el acceso a la cuenta de invitado. Puede ajustar esta configuración en [Azure Portal](https://portal.azure.com) en **Identidades externas / Configuración de colaboración externa:**

-   Para **el acceso de usuarios invitados,** los usuarios invitados tienen acceso limitado a propiedades y **pertenencias de objetos de directorio**
-   Para **la configuración de invitación de** invitado , establecer en Usuarios miembros y usuarios asignados a roles de administrador específicos pueden invitar a usuarios invitados, incluidos los **invitados con permisos de miembro**

Escritorio administrado de Microsoft requiere la siguiente configuración en la organización de Azure AD para el acceso a la cuenta de invitado. Puede ajustar esta configuración en [Azure Portal](https://portal.azure.com) en **Identidades externas / Configuración de colaboración externa:**

-   **Restricciones de colaboración,** elija cualquiera de estas opciones:
    -   Si selecciona Permitir **que las invitaciones se envíen a cualquier dominio (más inclusivo),** no se requiere ninguna otra configuración.
    -   Si selecciona Denegar invitaciones a los dominios **especificados,** asegúrese de que Microsoft.com no aparece en los dominios de destino.
    -   Si selecciona Permitir invitaciones solo a los dominios **especificados (más**  restrictivos), asegúrese de que Microsoft.com en los dominios de destino.

Si establece restricciones que interactúan con estas opciones de configuración, asegúrese de excluir las Azure Active Directory **modern Workplace Service Accounts**. Por ejemplo, si tiene una directiva de acceso condicional que impide que las cuentas de invitado tengan acceso al portal de Intune, excluya el grupo **Cuentas** de servicio de lugares de trabajo modernos de esta directiva.

Para obtener más información, vea [Habilitar la colaboración externa B2B y administrar quién puede invitar invitados.](/azure/active-directory/external-identities/delegate-invitations#to-configure-external-collaboration-settings)

## <a name="unlicensed-intune-admin"></a>Administrador de Intune sin licencia

La **configuración Permitir el acceso a administradores** sin licencia debe estar habilitada. Sin esta configuración habilitada, se pueden producir errores cuando intentamos tener acceso a la organización de Azure AD para el servicio. Puede habilitar esta configuración de forma segura sin preocuparse por las implicaciones de seguridad, ya que el ámbito de acceso lo definen los roles asignados a los usuarios, incluido nuestro personal de operaciones.

Para habilitar esta configuración, siga estos pasos:

1. Vaya al Centro Microsoft Endpoint Manager [administración.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. Vaya a **Administración de**  >  **inquilinos Roles**  >  **Licencias de administrador**.
3. En **Permitir el acceso a administradores sin** licencia, seleccione **Sí**.

> [!IMPORTANT]
> No puede deshacer esta configuración después de seleccionar **Sí**.

Para obtener más información, vea [Administradores sin licencia en Microsoft Intune](/mem/intune/fundamentals/unlicensed-admins).

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Pasos para prepararse para Escritorio administrado de Microsoft

1. Revisar los [requisitos previos del Escritorio administrado de Microsoft](prerequisites.md)
2. Ejecutar las [herramientas para evaluar la preparación](readiness-assessment-tool.md).
1. Comprar el [Portal de empresa](../get-started/company-portal.md).
1. Revise los requisitos previos de las cuentas invitadas (en este artículo).
1. Comprobar la [configuración de red](network.md).
1. [Preparar los certificados y perfiles de red](certs-wifi-lan.md).
1. [Preparar el acceso de usuario a los datos](authentication.md).
1. [Preparar las aplicaciones](apps.md).
1. [Preparar las unidades asignadas](mapped-drives.md).
1. [Preparar los recursos de impresión](printing.md).
1. [Nombres del dispositivo](address-device-names.md) de dirección.
