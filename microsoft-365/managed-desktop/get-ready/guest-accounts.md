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
ms.openlocfilehash: 6cd7b69d154444bb6b39e61bc3446ea01d54321a
ms.sourcegitcommit: b3091791196828883d8284497561027df692d109
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2021
ms.locfileid: "53663856"
---
# <a name="prerequisites-for-guest-accounts"></a>Requisitos previos para las cuentas de invitado

## <a name="external-collaboration-settings"></a>Configuración de la colaboración externa

Escritorio administrado de Microsoft requiere la siguiente configuración en la organización de Azure AD para el acceso a la cuenta de invitado. Puede ajustar esta configuración en [Azure Portal](https://portal.azure.com) en **Identidades externas / Configuración de colaboración externa:**

-   Para **las restricciones de invitación de invitado establecidas** en Usuarios miembros y usuarios asignados a roles de administrador específicos pueden invitar a usuarios **invitados,** incluidos los invitados con permisos de miembro
-   Para **restricciones de colaboración,** elija cualquiera de estas opciones:
    -   Si selecciona Permitir **que las invitaciones se envíen a cualquier dominio (más inclusivo),** no se requiere ninguna otra configuración.
    -   Si selecciona Denegar invitaciones a los dominios **especificados,** asegúrese de que Microsoft.com no aparece en los dominios de destino.
    -   Si selecciona Permitir invitaciones solo a los dominios **especificados (más**  restrictivos), asegúrese de que Microsoft.com en los dominios de destino.

Si establece restricciones que interactúan con estas opciones de configuración, asegúrese de excluir las Azure Active Directory **modern Workplace Service Accounts**. Por ejemplo, si tiene una directiva de acceso condicional que impide que las cuentas de invitado tengan acceso al portal de Intune, excluya el grupo **Cuentas** de servicio de lugares de trabajo modernos de esta directiva.

## <a name="unlicensed-intune-admin"></a>Administrador de Intune sin licencia

La **configuración Permitir el acceso a administradores** sin licencia debe estar habilitada. Sin esta configuración habilitada, se pueden producir errores cuando intentamos tener acceso a la organización de Azure AD para el servicio. Puede habilitar esta configuración de forma segura sin preocuparse por las implicaciones de seguridad, ya que el ámbito de acceso lo definen los roles asignados a los usuarios, incluido nuestro personal de operaciones.

Para habilitar esta configuración, siga estos pasos:

1. Vaya al Centro Microsoft Endpoint Manager [administración.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. Vaya a **Administración de**  >  **inquilinos Roles**  >  **Licencias de administrador**.
3. En **Permitir el acceso a administradores sin** licencia, seleccione **Sí**.

> [!IMPORTANT]
> No puede deshacer esta configuración después de seleccionar **Sí**.

Para obtener más información, vea [Administradores sin licencia en Microsoft Intune](/mem/intune/fundamentals/unlicensed-admins).

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
