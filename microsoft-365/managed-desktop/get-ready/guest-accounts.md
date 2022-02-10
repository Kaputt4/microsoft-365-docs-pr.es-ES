---
title: Requisitos previos para las cuentas de invitado
description: Directrices de configuración para cuentas de invitado y cómo ajustarlas
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 80770c6c122cc4e2892c22a43f185ffbac40c637
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520419"
---
# <a name="prerequisites-for-guest-accounts"></a>Requisitos previos para las cuentas de invitado

## <a name="external-collaboration-settings"></a>Configuración de la colaboración externa

Microsoft Managed Desktop recomienda la siguiente configuración en su Azure AD para el acceso a la cuenta de invitado. Puede ajustar esta configuración en [Azure Portal](https://portal.azure.com) en **Identidades externas / Configuración de colaboración externa**:

| Configuración | Establecer como |
| ------ | ------ |
| Acceso de invitado | Los invitados tienen acceso limitado a propiedades y pertenencias a objetos de directorio. |
| Configuración de invitaciones para usuarios invitados | Los usuarios miembros y los usuarios asignados a roles de administrador específicos pueden invitar a invitados, incluidos los invitados con permisos de miembro |

Microsoft Managed Desktop requiere la siguiente configuración en su Azure AD para el acceso a la cuenta de invitado. Puede ajustar esta configuración en [Azure Portal](https://portal.azure.com) en **Identidades externas / Configuración de colaboración externa**:

| Configuración | Opción |
| ------ | ------ |
| Restricciones de colaboración | Seleccione cualquiera de estas opciones: <ul><li>Si selecciona Permitir **que las invitaciones se envíen a cualquier dominio (más inclusivo),** no se requiere ninguna otra configuración.</li><li>Si selecciona **Denegar invitaciones** a los dominios especificados, asegúrese de Microsoft.com no aparece en los dominios de destino.</li><li>Si selecciona **Permitir invitaciones solo a los dominios especificados (** más restrictivos), asegúrese de que Microsoft.com aparece en los dominios  de destino.</li><ul>

Si establece restricciones que interactúan con esta configuración, asegúrese de excluir las Azure Active Directory **modernas de servicio workplace**. Por ejemplo, si tiene una directiva de acceso condicional que impide que las cuentas de invitado tengan acceso al portal de Intune, excluya el grupo **Cuentas** de servicio de lugares de trabajo modernos de esta directiva.

Para obtener más información, vea [Habilitar la colaboración externa B2B y administrar quién puede invitar invitados](/azure/active-directory/external-identities/delegate-invitations#to-configure-external-collaboration-settings).

## <a name="unlicensed-intune-admin"></a>Administrador de Intune sin licencia

La **configuración Permitir el acceso a administradores** sin licencia debe estar habilitada. Sin esta configuración habilitada, pueden producirse errores cuando intentamos tener acceso a su Azure AD organización para el servicio. Puedes habilitar esta configuración de forma segura sin preocuparte por las implicaciones de seguridad. El ámbito de acceso lo definen los roles asignados a los usuarios, incluido nuestro personal de operaciones.

**Para habilitar esta configuración:**

1. Vaya al Centro Microsoft Endpoint Manager [administración](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vaya a **Administración de inquilinos**, **seleccione Roles**. A continuación, seleccione **Licencias de administrador**.
3. En la **sección Permitir acceso a administradores** sin licencia, seleccione **Sí**.

> [!IMPORTANT]
> No puede deshacer esta configuración después de seleccionar **Sí**.

Para obtener más información, vea [Administradores sin licencia en Microsoft Intune](/mem/intune/fundamentals/unlicensed-admins).

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Pasos para prepararse para El escritorio administrado de Microsoft

1. Revisar los [requisitos previos del Escritorio administrado de Microsoft](prerequisites.md)
1. Ejecutar las [herramientas para evaluar la preparación](readiness-assessment-tool.md).
1. Comprar el [Portal de empresa](../get-started/company-portal.md).
1. Revise los requisitos previos de las cuentas invitadas (en este artículo).
1. Comprobar la [configuración de red](network.md).
1. [Preparar los certificados y perfiles de red](certs-wifi-lan.md).
1. [Preparar el acceso de usuario a los datos](authentication.md).
1. [Preparar las aplicaciones](apps.md).
1. [Preparar las unidades asignadas](mapped-drives.md).
1. [Preparar los recursos de impresión](printing.md).
1. [Nombres del dispositivo](address-device-names.md) de dirección.
