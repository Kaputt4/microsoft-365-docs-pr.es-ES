---
title: Instalar Portal de empresa de Intune dispositivos
description: Información sobre cómo instalar la aplicación del portal de empresa en dispositivos de Escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, Portal de empresa
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: c7edc974bfd4a4f0d2d9611c80d0996aebc3ddb7
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326872"
---
# <a name="install-intune-company-portal-on-devices"></a>Instalar Portal de empresa de Intune dispositivos

Microsoft Managed Desktop requiere que los administradores de TI instalen el Portal de empresa de Intune para sus usuarios con dispositivos de Escritorio administrado de Microsoft. Las ventajas para su organización incluyen:

- Los usuarios tienen un lugar para examinar e instalar aplicaciones disponibles.
- Los administradores de TI pueden organizar las aplicaciones por categorías para sus usuarios.  
- Algunas aplicaciones (como Microsoft Project y Microsoft Visio) requieren Portal de empresa implementar con Microsoft Managed Desktop.
- Los administradores de TI pueden personalizar Portal de empresa para su organización. Las personalizaciones incluyen la creación de imágenes de marca, la adición de contactos de soporte técnico local y mucho más. Para obtener más información, [consulta How to Configure the Microsoft Intune Portal de empresa app](/intune/company-portal-app).

En este artículo se documenta el proceso para implementar el Portal de empresa de Intune a los usuarios de Escritorio administrado de Microsoft. El proceso general tiene este aspecto:

1. [Compre Portal de empresa desde Microsoft Store para Empresas y sincronice con Intune](#step-1-purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune).
2. [Asigne Portal de empresa a los usuarios](#step-2-assign-company-portal-to-your-users).
3. [Comunicar el cambio a los usuarios.](#step-3-communicate-change-to-your-users)

## <a name="step-1-purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Paso 1: Comprar Portal de empresa desde Microsoft Store para Empresas y sincronizar con Intune

Para obtener información sobre cómo comprar las aplicaciones y sincronizarlas con Intune, consulta [Microsoft Store para Empresas aplicaciones](deploy-apps.md#msfb-apps) en Implementar aplicaciones en dispositivos *de Escritorio administrado de Microsoft*.

En este artículo se proporciona información sobre cómo:

- Comprar Portal de empresa desde Microsoft Store para Empresas.
- Forzar la sincronización entre Intune y Microsoft Store para Empresas.
- Compruebe la sincronización activa entre Intune y Microsoft Store para Empresas.

## <a name="step-2-assign-company-portal-to-your-users"></a>Paso 2: Asignar Portal de empresa a los usuarios

Después de la inscripción en Microsoft Managed Desktop, implementaremos automáticamente Portal de empresa tu inquilino e instalaremos la aplicación en dispositivos de Escritorio administrado de Microsoft en tu organización.

## <a name="step-3-communicate-change-to-your-users"></a>Paso 3: Comunicar el cambio a los usuarios

Como administrador de TI de su organización, es importante que los usuarios sepan cómo usar Portal de empresa en su organización. Microsoft Managed Desktop recomienda:

- Pasos para instalar aplicaciones desde el Portal de empresa. Para obtener más información, consulta [Instalar y compartir aplicaciones en el dispositivo](/intune-user-help/install-apps-cpapp-windows).
- Cómo enviar solicitudes a los administradores de TI para aplicaciones que no están disponibles actualmente. Para obtener más información, consulta [Solicitar una aplicación para el trabajo o la escuela](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

1. Acceder al [portal de administrador](access-admin-portal.md).
1. [Agregar y verificar los contactos de administración en el portal de administrador](add-admin-contacts.md).
1. [Ajustar la configuración después de la inscripción](conditional-access.md).
1. Implemente y asigne Portal de empresa de Intune (este artículo).
1. [Asignar las licencias](assign-licenses.md).
1. [Implementar las aplicaciones](deploy-apps.md).
1. [Preparar dispositivos](prepare-devices.md)
1. Configurar la [experiencia de primera ejecución con el Autopilot y la página de estado de inscripción](esp-first-run.md).
1. [Habilitar las características de soporte técnico para el usuario](enable-support.md).
1. [Preparar a los usuarios para que usen los dispositivos](get-started-devices.md).
1. [Comenzar a usar el control de aplicaciones](get-started-app-control.md).
